# syntax=docker/dockerfile:1
FROM ubuntu:20.04

RUN apt-get update && apt-get install -y \
	openssh-client \
	vim \
	x11-apps \
	net-tools
COPY .bashrc /root/.bashrc
COPY .ssh/id_rsa /root/.ssh/id_rsa 
COPY .ssh/id_rsa.pub /root/.ssh/id_rsa.pub
EXPOSE 22
