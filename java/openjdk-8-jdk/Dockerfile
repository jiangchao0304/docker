#
# OpenJDK Java 7 JDK Dockerfile
#
# https://github.com/jc0304/docker
# https://github.com/dockerfile/java/tree/master/openjdk-6-jdk
#

FROM centos

MAINTAINER jc0304 <14317048@qq.com>

# Install wget.
RUN yum ( install -y  wget && mkdir /opt/java )


# Install Java.
RUN wget --no-cookies --no-check-certificate \
         --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F;oraclelicense=accept-securebackup-cookie"  \
		 "http://download.oracle.com/otn-pub/java/jdk/7u79-b15/jdk-7u79-linux-x64.tar.gz" 


#解压并删除下载的包
RUN tar xvf jdk-7u79-linux-x64.tar.gz -C /opt/java && \
    rm -rf jdk-7u79-linux-x64.tar.gz && 

#配置JAVA_HOME 

ENV JAVA_HOME=/opt/java/jdk1.7.0_79 
ENV JRE_HOME $JAVA_HOME/jre 
ENV PATH=$PATH:$JAVA_HOME/bin:$JRE_HOME/lib
ENV CLASSPATH=$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar 

CMD ["/bin/bash"]





