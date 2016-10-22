# VERSION 2.19.1

FROM jc0304/java:7

MAINTAINER jc0304 <14317048@qq.com>


RUN mkdir /opt/maven
RUN mkdir /opt/jenkins

RUN (yum install -y nano wget git)


#下载maven
RUN wget http://apache.fayea.com/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz  


#解压并删除下载的包
RUN tar xvf apache-maven-3.3.9-bin.tar.gz -C /opt/maven && \
	rm -rf apache-maven-3.3.9-bin.tar.gz 

ENV MAVEN_HOME  /opt/maven/apache-maven-3.3.9

ENV PATH $PATH:$MAVEN_HOME/bin

#安装jenkins
RUN wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
RUN rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
RUN yum install -y jenkins
# http://mirrors.jenkins-ci.org/war/latest/jenkins.war

EXPOSE 8080

#CMD exec java  -jar /opt/jenkins/jenkins.war 

ENTRYPOINT ["java","-jar","/usr/lib/jenkins/jenkins.war"]




