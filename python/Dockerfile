FROM python:2.7.12
MAINTAINER Bruce
ENV REFRESHED_AT 2016-10-09

# ubuntu 16.*
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN mv /etc/apt/sources.list /etc/apt/sources.list.bak
ADD sources.list /etc/apt/
RUN apt-get -yqq update

# 文件目录
ARG APP_DIR=/usr/opt/app
# 依赖的文件名称
ARG REQ_FILE=req.txt
ADD $REQ_FILE $APP_DIR

RUN mkdir -p $APP_DIR
WORKDIR $APP_DIR

ONBUILD RUN pip install --no-cache-dir -r $REQ_FILE  -i https://mirrors.ustc.edu.cn/pypi/web/simple --trusted-host=mirrors.ustc.edu.cn

EXPOSE 5000
CMD ["./runserver.sh"]
