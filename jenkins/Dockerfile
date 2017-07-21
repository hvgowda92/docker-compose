FROM ubuntu:14.04

MAINTAINER me

# Install java 8
RUN apt-get update
RUN apt-get install -y software-properties-common
RUN add-apt-repository -y ppa:webupd8team/java
RUN apt-get update
RUN echo debconf shared/accepted-oracle-license-v1-1 select true | sudo debconf-set-selections
RUN echo debconf shared/accepted-oracle-license-v1-1 seen true | sudo debconf-set-selections
RUN apt-get install -y oracle-java8-installer

# Install Jenkins
RUN wget -q -O - https://pkg.jenkins.io/debian/jenkins-ci.org.key | sudo apt-key add -
RUN echo deb http://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list
RUN sudo apt-get update
RUN sudo apt-get install -y jenkins

# Install Git
RUN apt-get install -y git

# Install Maven
RUN apt-get install -y maven

EXPOSE 8080

ENV JENKINS_HOME /jenkins

CMD ["java", "-jar", "/usr/share/jenkins/jenkins.war"]
