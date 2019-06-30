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

# Install Oracle JDK 8u45
RUN -ex
cd /tmp && \
    curl -L -O -H "Cookie: oraclelicense=accept-securebackup-cookie" -k "http://download.oracle.com/otn-pub/java/jdk/8u45-b14/jdk-8u45-linux-x64.rpm" && \
    yum localinstall -y jdk-8u45-linux-x64.rpm && \
    rm -f jdk-8u45-linux-x64.rpm 

# Define commonly used JAVA_HOME variable
ENV JAVA_HOME /usr/java/default

# Add jdk on PATH variable
ENV PATH ${PATH}:${JAVA_HOME}/bin
