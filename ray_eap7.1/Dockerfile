FROM rayho8224/centos
COPY jboss-eap-7.1 /home/jboss-eap-7.1
WORKDIR /home

COPY supervisord.conf /etc/supervisord.conf  
CMD ["/usr/bin/supervisord"]