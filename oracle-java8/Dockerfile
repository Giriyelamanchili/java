#
# Oracle Java 8 Dockerfile
#
# https://github.com/dockerfile/java
# https://github.com/dockerfile/java/tree/master/oracle-java8
#

# Pull base image.
FROM dockerfile/ubuntu

# Install Java.
RUN \
  echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
  add-apt-repository -y ppa:webupd8team/java && \
  apt-get update && \
  apt-get install -y oracle-java8-installer && \
  rm -rf /var/lib/apt/lists/* && \
  rm -rf /var/cache/oracle-jdk8-installer


# Define working directory.
WORKDIR /data

# Define commonly used JAVA_HOME variable
ENV JAVA_HOME /usr/lib/jvm/java-8-oracle

# Define default command.
CMD ["bash"]
RUN wget wget http://redrockdigimark.com/apachemirror/tomcat/tomcat-8/v8.5.24/bin/apache-tomcat-8.5.24-deployer.tar.gz
RUN tar xvzf apache-tomcat-8.5.24-deployer.tar.gz
RUN mv apache-tomcat-8.5.24 tomcat8
CMD ["tomcat8/bin/catlina.sh","run"]
