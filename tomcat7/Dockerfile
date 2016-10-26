# VERSION 0.0.1

FROM centos


MAINTAINER jc0304 <14317048@qq.com>





RUN  ( yum install -y  wget && mkdir /opt/java && mkdir /opt/tomcat )

# get jdk.
RUN wget --no-cookies --no-check-certificate \
         --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F;oraclelicense=accept-securebackup-cookie"  \
		 "http://download.oracle.com/otn-pub/java/jdk/7u79-b15/jdk-7u79-linux-x64.tar.gz" 
		 
# get tomcat.	 
RUN wget http://apache.fayea.com/tomcat/tomcat-7/v7.0.72/bin/apache-tomcat-7.0.72.tar.gz


# install
RUN tar xvf jdk-7u79-linux-x64.tar.gz -C /opt/java && \
	rm -rf jdk-7u79-linux-x64.tar.gz && \
	tar xvf apache-tomcat-7.0.72.tar.gz -C /opt && /
	mv /opt/apache-tomcat-7.0.72/ /opt/tomcat && /
	rm -rf apache-tomcat-7.0.72 && /
	rm -rf apache-tomcat-6.0.45.tar.gz

#配置JAVA_HOME 

ENV JAVA_HOME=/opt/java/jdk1.7.0_79
ENV JRE_HOME $JAVA_HOME/jre
ENV PATH=$PATH:$JAVA_HOME/bin:$JRE_HOME/lib
ENV CLASSPATH=$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
	
# 容器需要开放Tomcat 8080端口
EXPOSE 8080

# 设置Tomcat7作为后台运行
ENTRYPOINT /opt/tomcat/bin/startup.sh && tail -f /opt/tomcat/logs/catalina.out

