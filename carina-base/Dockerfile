# Docker Buile file for Carina - Base 
# ---------------------------------------------------
 
FROM           kweku360/carina-base
MAINTAINER     Kweku Kankam <kweku360@gmail.com>

#Compile and update unbuntu source lists
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y

#Install SSH and Apache daemons as well as Supervisor in our container
RUN apt-get install -y openssh-server apache2 supervisor
RUN mkdir -p /var/run/sshd
RUN mkdir -p /var/log/supervisor

#Change Root Password for ssh
RUN  echo "root:theProfit" | chpasswd
#RUN echo -e "theProfit\ntheProfit" | (passwd --stdin $USER)

#Add Configuration File Supervisor
ADD sourcefiles/supervisord.conf /etc/supervisor/conf.d/supervisord.conf

#Expose Ports and Start Supervisor daemon
EXPOSE 22 80
CMD ["/usr/bin/supervisord"]
