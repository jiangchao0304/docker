# VERSION 2.14

FROM centos

MAINTAINER jc0304 <14317048@qq.com>

# Install wget.
RUN  ( yum install -y  wget && mkdir /opt/nexus  && mkdir /opt/maven && mkdir /opt/java)


# Install Java.
RUN ( wget --no-cookies --no-check-certificate \
         --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F;oraclelicense=accept-securebackup-cookie"  \
		 "http://download.oracle.com/otn-pub/java/jdk/7u79-b15/jdk-7u79-linux-x64.tar.gz"  && \
		 wget http://apache.fayea.com/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz   && \
		 wget http://www.sonatype.org/downloads/nexus-latest-bundle.tar.gz  )

#下载maven
#RUN wget http://apache.fayea.com/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz  

#下载nexus
#RUN wget http://www.sonatype.org/downloads/nexus-latest-bundle.tar.gz




#解压并删除下载的包
RUN tar xvf nexus-latest-bundle.tar.gz -C /opt/nexus && \
    rm -rf nexus-latest-bundle.tar.gz  && \
	tar xvf apache-maven-3.3.9-bin.tar.gz -C /opt/maven && \
	rm -rf apache-maven-3.3.9-bin.tar.gz  && \
	tar xvf jdk-7u79-linux-x64.tar.gz -C /opt/java && \
    rm -rf jdk-7u79-linux-x64.tar.gz

ENV JAVA_HOME /opt/java/jdk1.7.0_79

ENV JRE_HOME $JAVA_HOME/jre

ENV CLASSPATH $JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar	

ENV MAVEN_HOME  /opt/maven/apache-maven-3.3.9

ENV PATH $PATH:$MAVEN_HOME/bin:$JAVA_HOME/bin:

ENV RUN_AS_USER root

ENTRYPOINT ["./opt/nexus/nexus-2.14.0-01/bin/nexus","start"]





