# VERSION 0.0.1
# 默认ubuntu server长期支持版本，当前是12.04

FROM centos

#sign info

MAINTAINER jc0304 <14317048@qq.com>


ENV MAVEN_VERSION 3.3.9

#install wget

RUN mkdir /opt/java 

RUN mkdir /opt/maven

RUN yum install -y nano wget

#下载JDK7
RUN wget --no-cookies --no-check-certificate \
         --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F;oraclelicense=accept-securebackup-cookie"  \
		 "http://download.oracle.com/otn-pub/java/jdk/7u79-b15/jdk-7u79-linux-x64.tar.gz" 

#下载maven
RUN wget http://apache.fayea.com/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz 

#解压并删除下载的包
RUN tar xvf jdk-7u79-linux-x64.tar.gz -C /opt/java && \
    rm -rf jdk-7u79-linux-x64.tar.gz && \
	tar xvf apache-maven-3.3.9-bin.tar.gz -C /opt/maven && \
	rm -rf apache-maven-3.3.9-bin.tar.gz

#配置JAVA_HOME M2_HOME

ENV JAVA_HOME=/opt/java/jdk1.7.0_79 
ENV PATH=$PATH:/opt/maven/apache-maven-3.3.9/bin:$JAVA_HOME/bin 
ENV CLASSPATH=$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar 

#安装jenkins
RUN wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
RUN rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
RUN yum install -y jenkins



# 容器需要开放Tomcat 8080端口
#EXPOSE 8080

# 设置Tomcat7作为后台运行
#ENTRYPOINT /opt/tomcat/bin/startup.sh && tail -f /opt/tomcat/logs/catalina.out




