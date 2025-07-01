制作Dockerfile时

网络要翻墙
192.168.0.89

/etc/docker/daemon.json
增加
 "insecure-registries": ["192.168.0.98:80"]




FROM python:3.10-slim 
#FROM 192.168.0.98:80/ym_offline/python-base-smart:v1.0.0
#FROM python-base-smart:1.0

WORKDIR /install

# 使用国内源，加速安装（可选）
#RUN rm /install/requirements.txt
COPY requirements.txt .

RUN python3 -m pip install --upgrade pip && python3 -m pip install --default-timeout=3600 --no-cache-dir -r requirements.txt --index-url http://192.168.0.83:8081/repository/pypi_group/simple --trusted-host 192.168.0.83


docker build .
