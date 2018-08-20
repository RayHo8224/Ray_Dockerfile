FROM rayho8224/centos

# install apache httpd server
RUN yum install -y httpd

# override supervisord.conf
COPY supervisord.conf /etc/supervisord.conf  
# auto execute CMD ["/usr/bin/supervisord"]  

