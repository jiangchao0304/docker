
FROM jc0304/java:7

MAINTAINER jc0304 <14317048@qq.com>

# Install wget.
RUN  ( yum install -y  wget && mkdir /opt/nexus  && mkdir /opt/maven)

#下载maven
RUN wget http://apache.fayea.com/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz  

#下载nexus
RUN wget http://www.sonatype.org/downloads/nexus-latest-bundle.tar.gz




#解压并删除下载的包
RUN tar xvf nexus-latest-bundle.tar.gz -C /opt/nexus && \
    rm -rf nexus-latest-bundle.tar.gz  && \
	tar xvf apache-maven-3.3.9-bin.tar.gz -C /opt/maven && \
	rm -rf apache-maven-3.3.9-bin.tar.gz 

ENV MAVEN_HOME  /opt/maven/apache-maven-3.3.9

ENV PATH $PATH:$MAVEN_HOME/bin

ENV RUN_AS_USER root

ENTRYPOINT ["./opt/nexus/nexus-2.14.0-01/bin/nexus","start"]





