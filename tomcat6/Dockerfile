# VERSION 0.0.1
# 默认ubuntu server长期支持版本，当前是12.04

FROM centos

#sign info

MAINTAINER jc0304 <14317048@qq.com>

#update yum  
#RUN yum -y install wget

#RUN mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
#RUN wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyuncs.com/repo/Centos-7.repo
#RUN yum makecache
#RUN yum update -y
#RUN yum upgrade -y

#install jdk
RUN yum -y install java-1.6.0-openjdk.x86_64 wget

RUN wget http://mirrors.hust.edu.cn/apache/tomcat/tomcat-6/v6.0.47/bin/apache-tomcat-6.0.47.tar.gz

RUN tar xvf apache-tomcat-6.0.47.tar.gz -C /opt && \
     mv /opt/apache-tomcat-6.0.47/ /opt/tomcat && \
	 rm -rf apache-tomcat-6.0.47 && \
	 rm -rf apache-tomcat-6.0.47.tar.gz

# 容器需要开放Tomcat 8080端口
EXPOSE 8080

# 设置Tomcat7作为后台运行
ENTRYPOINT /opt/tomcat/bin/startup.sh && tail -f /opt/tomcat/logs/catalina.out

