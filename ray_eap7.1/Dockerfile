FROM rayho8224/centos

# copy jboss-eap-7.1 to container
COPY jboss-eap-7.1 /home/jboss-eap-7.1
WORKDIR /home

# override supervisord.conf
COPY supervisord.conf /etc/supervisord.conf  
# auto execute CMD ["/usr/bin/supervisord"]  
