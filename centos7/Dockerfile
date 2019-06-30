FROM centos
MAINTAINER linkeer8802 <linkeer8802@gmail.com>
RUN ln -sf \
		/usr/share/zoneinfo/Asia/Shanghai \
		/etc/localtime \
	&& echo "NETWORKING=yes" > /etc/sysconfig/network
# -----------------------------------------------------------------------------
# Ulimit
RUN echo "* soft nofile 655350" >> /etc/security/limits.conf & \
echo "* hard nofile 655350" >> /etc/security/limits.conf & \
echo "@root        soft    nproc           655350" >> /etc/security/limits.conf & \
echo "@root        hard    nproc           655350" >> /etc/security/limits.conf & \
echo "ulimit -SH 655350" >> /etc/rc.local
