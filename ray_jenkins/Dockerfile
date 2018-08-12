FROM jenkins:latest
# if we want to install via apt
USER root
RUN apt-get update && apt-get install -y vim
#set time zone = Taipei +8
ENV TZ=Asia/Taipei
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
# drop back to the regular jenkins user - good practice
USER jenkins