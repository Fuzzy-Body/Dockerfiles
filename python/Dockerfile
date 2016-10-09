FROM python:2.7.12
MAINTAINER Bruce
ENV REFRESHED_AT 2016-10-09

# ubuntu
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN sudo mv /etc/apt/sources.list /etc/apt/sources.list.bak
ADD sources.list /etc/apt/
RUN sudo apt-get -yqq update

# 文件目录
ENV APP_DIR .
# 依赖的文件名称
ENV REQ_FILE req.txt

VOLUME $APP_DIR
WORKDIR $APP_DIR

ONBUILD RUN pip install --no-cache-dir -r $REQ_FILE  -i https://mirrors.ustc.edu.cn/pypi/web/simple --trusted-host=mirrors.ustc.edu.cn
