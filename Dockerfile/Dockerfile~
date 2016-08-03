FROM ubuntu:14.04
ENV http_proxy http://pr325431:Sentry123@10.201.51.71:8080/
ENV https_proxy https://pr325431:Sentry123@10.201.51.71:8080/
RUN echo $http_proxy
RUN echo $https_proxy
COPY apt.conf /etc/apt/apt.conf
RUN cat /etc/apt/apt.conf
RUN sudo apt-get update
RUN sudo apt-get install -y software-properties-common python-software-properties
RUN sudo -E add-apt-repository ppa:openjdk-r/ppa
RUN sudo apt-get update
RUN sudo apt-get install -y openjdk-8-jdk
RUN java -version
RUN sudo apt-get install -y apt-transport-https ca-certificates
RUN sudo apt-key adv --keyserver-options http-proxy=http://pr325431:Sentry123@10.201.51.71:8080 --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
RUN echo "deb https://apt.dockerproject.org/repo ubuntu-trusty main" >> /etc/apt/sources.list.d/docker.list
RUN sudo apt-get update
RUN apt-cache policy docker-engine
RUN sudo apt-get update
RUN  sudo apt-get install -y docker-engine
RUN sudo service docker start
RUN sudo apt-get install -y git
RUN sudo apt-get install -y apt-cacher apache2
RUN sudo apt-get install -y bind9
