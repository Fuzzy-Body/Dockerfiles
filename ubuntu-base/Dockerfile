FROM ubuntu:14.04
MAINTAINER Bruce
ENV REGRESHED_AT 2016-10-09

# 重要:设置image的时区
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN mv /etc/apt/sources.list /etc/apt/sources.list.bak
ADD sources.list /etc/apt/

RUN apt-get -yqq update
