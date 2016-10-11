FROM python:2.7.12
MAINTAINER Bruce
ENV REFRESHED_AT 2016-10-11

# ubuntu 16.*
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
ONBUILD RUN apt-get -yqq update

# 文件目录
ARG APP_DIR=/opt/app/
# 依赖的文件路径
ARG requirement=requirement.txt
COPY $requirement /tmp/requirements.txt

WORKDIR $APP_DIR

RUN pip install --no-cache-dir -r /tmp/requirements.txt  \
-i https://mirrors.ustc.edu.cn/pypi/web/simple --trusted-host=mirrors.ustc.edu.cn

EXPOSE 5000
CMD ["./runserver.sh"]
