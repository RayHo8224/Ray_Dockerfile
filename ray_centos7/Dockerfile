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
RUN mkdir /var/run/sshd
RUN ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key -N '' 

#install openjdk8 & setting ENV
RUN yum install -y java-1.8.0-openjdk-devel
RUN echo "export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk" >> ~/.bashrc
#####ENV JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk
#####ENV PATH=$JAVA_HOME/bin:$PATH

#install maven3.5.4 & setting ENV
COPY apache-maven-3.5.4-bin.zip /opt/
RUN unzip /opt/apache-maven-3.5.4-bin.zip -d /opt
RUN rm -f /opt/apache-maven-3.5.4-bin.zip
#####ENV PATH=/opt/apache-maven-3.5.4/bin:$PATH

#setting $PATH
RUN echo "export PATH=/opt/apache-maven-3.5.4/bin:/usr/lib/jvm/java-1.8.0-openjdk/bin:$PATH" >> ~/.bashrc

#install supervisor
RUN yum install -y python-setuptools  
RUN easy_install supervisor  
RUN mkdir -p /var/log/supervisor

#startup supervisord
COPY supervisord.conf /etc/supervisord.conf  
CMD ["/usr/bin/supervisord"]  

