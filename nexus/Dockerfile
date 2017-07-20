FROM ubuntu:14.04

MAINTAINER me

RUN apt-get update
RUN apt-get install -y software-properties-common
RUN add-apt-repository -y ppa:webupd8team/java
RUN apt-get update
RUN echo debconf shared/accepted-oracle-license-v1-1 select true | sudo debconf-set-selections
RUN echo debconf shared/accepted-oracle-license-v1-1 seen true | sudo debconf-set-selections
RUN apt-get install -y oracle-java8-installer

RUN wget http://download.sonatype.com/nexus/3/nexus-3.4.0-02-unix.tar.gz
RUN tar xvzf nexus-3.4.0-02-unix.tar.gz
RUN ln -s nexus-3.4.0-02 nexus

EXPOSE 8081

CMD ["nexus/bin/nexus", "run"]
