# syntax=docker/dockerfile:1
FROM ubuntu:20.04

RUN apt-get update && apt-get install -y \
	openssh-server \
	supervisor \
	vim \
	net-tools \
	x11-apps
RUN mkdir -p /var/log/supervisor /var/run/sshd /root/.ssh/
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
COPY .ssh/id_rsa.pub /root/.ssh/id_rsa.pub
COPY .ssh/id_rsa2.pub /root/.ssh/id_rsa2.pub
COPY .ssh/id_rsa2 /root/.ssh/id_rsa2
COPY sshd_config /etc/ssh/sshd_config
COPY .bashrc /root/.bashrc
RUN touch /root/.ssh/authorized_keys && cat /root/.ssh/id_rsa.pub >> /root/.ssh/authorized_keys && rm /root/.ssh/id_rsa.pub
EXPOSE 22
CMD ["/usr/bin/supervisord"]
