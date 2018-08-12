FROM centos:centos7

#set time zone = Taipei +8
ENV TZ=Asia/Taipei
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

#install vim
RUN yum install -y vim

#install unzip
RUN yum install -y unzip

#install ssh
RUN yum install -y openssh-server openssh-clients

#install openjdk8 & setting ENV
RUN yum install -y java-1.8.0-openjdk-devel
ENV JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk
ENV PATH=$JAVA_HOME/bin:$PATH

#install maven3.5.4 & setting ENV
COPY apache-maven-3.5.4-bin.zip /opt/
RUN unzip /opt/apache-maven-3.5.4-bin.zip -d /opt
RUN rm -f /opt/apache-maven-3.5.4-bin.zip
ENV PATH=/opt/apache-maven-3.5.4/bin:$PATH
