# Updated as of July 17, 2017
# Install FROM UBUNTU IMAGE
FROM ubuntu:16.04

# Author
MAINTAINER Akshathkumar Shetty

# Run an update to get all the security patches
RUN apt-get update && apt-get -y upgrade
RUN apt-get -y install software-properties-common
RUN add-apt-repository ppa:webupd8team/java

#The below instruction is very important, failing to add this will not allow you to install JDK
# after the repository has been added.
RUN apt-get -y update

#Install curl/vim incase you want to debug. 
#nano - nano editor, 
#curl is a utility which acts as http client which can be run from the unix prompt.
RUN apt-get -y install curl nano

# Accept the license
RUN echo "oracle-java8-installer shared/accepted-oracle-license-v1-1 boolean true" | debconf-set-selections
RUN apt-get -y install oracle-java8-installer

# Define commonly used JAVA_HOME variable
ENV JAVA_HOME /usr/lib/jvm/java-8-oracle