# Docker image of simple VNC server
# ---------------------------------------------------
 
FROM            88ba7f12a8d0
MAINTAINER     Misho Krastev <misho.kr@gmail.com>

# Setup minimal X server -----
ADD openbox.autostart /.config/openbox/autostart
ADD openbox.rc.xml /.config/openbox/rc.xml

RUN mkdir /.config/fbpanel && cp /usr/share/fbpanel/default /.config/fbpanel/default

# Configure supervisord -----
ADD supervisord.conf /etc/
ADD supervisor.xvfb.conf /etc/supervisord.d/
ADD supervisor.x11vnc.conf /etc/supervisord.d/
ADD supervisor.sshd.conf /etc/supervisord.d/
 
# SSH port, no direct connections to VNC server
EXPOSE 22

CMD [ "/usr/bin/supervisord", "-c", "/etc/supervisord.conf" ]

# ENV LC_ALL      en_US.UTF-8

# ---------------------------------------------------
# eof