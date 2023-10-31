# build with host mode: -t means tag
# `docker build --network host -t deego/salepred:1.0 .`

# debian 11 https://hub.docker.com/_/python shared tages 适用于arm和amd64
FROM python:3.10.13-bullseye

# 设置工作目录和user
WORKDIR /workspace
USER root

# 基本环境
## debian 11 自带 gcc git curl ...
# RUN apt update && \
#     apt install git
RUN apt update && \
    apt-get install nano

# --- python pakgs ---
# 复制本地文件到容器中  
COPY requirements.txt .

# # 安装Python依赖z 
RUN pip install --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt


# docker run --network host --name salepred -v "%cd%:/workspace"  -it deego/salepred:1.0
# --gpus all
