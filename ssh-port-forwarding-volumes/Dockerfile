
FROM	    centos:latest
MAINTAINER  aman@localhost
RUN	    yum install -y --downloadonly --downloaddir=/mnt vsftpd
RUN 	    yum install -y passwd
RUN	    su -   \ 
	    && echo "a" | passwd --stdin root \
	    && mkdir /home/personal 
RUN 	    yum install -y openssh-server \
	    && ssh-keygen -A  \
	    && echo "Port 2424" >> /etc/ssh/sshd_config 
CMD	    ["/usr/sbin/sshd","-D"]
EXPOSE 	    2424
VOLUME 	    /home/personal
