# VERSION 0.0.1
# 默认ubuntu server长期支持版本，当前是12.04

FROM jc0304/java:7

#sign info

MAINTAINER jc0304 <14317048@qq.com>


ENV MAVEN_VERSION 3.3.9

#install wget



RUN mkdir /opt/maven

RUN yum install -y nano wget


#下载maven
RUN wget http://apache.fayea.com/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz 

#解压并删除下载的包
RUN tar xvf apache-maven-3.3.9-bin.tar.gz -C /opt/maven && \
	rm -rf apache-maven-3.3.9-bin.tar.gz




ENV MAVEN_HOME =/opt/maven/apache-maven-3.3.9

ENV PATH=$PATH:$MAVEN_HOME/bin


#安装jenkins
RUN wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
RUN rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
RUN yum install -y jenkins
# http://mirrors.jenkins-ci.org/war/latest/jenkins.war
EXPOSE 8080

CMD exec java  -jar /usr/lib/jenkins/jenkins.war 

#RUN (wget && wget && tar)
# 设置Tomcat7作为后台运行
#ENTRYPOINT /opt/tomcat/bin/startup.sh && tail -f /opt/tomcat/logs/catalina.out
#ENTRYPOINT ["java","-jar","/usr/lib/jenkins/jenkins.war"]




