FROM ubuntu:14.04
MAINTAINER Bruce
ENV REGRESHED_AT 2016-10-09

RUN sudo mv /etc/apt/sources.list /etc/apt/sources.list.bak
ADD sources.list /etc/apt/

RUN sudo apt-get -yqq update
