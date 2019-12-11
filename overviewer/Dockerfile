FROM ubuntu:18.04

RUN apt-get update \
&& apt-get install -y wget apt-transport-https gnupg2 cron \
&& echo 'deb https://overviewer.org/debian ./' >> /etc/apt/sources.list \
&& wget -O - https://overviewer.org/debian/overviewer.gpg.asc | apt-key add - \
&& apt-get update \
&& apt-get install -y minecraft-overviewer \
&& wget https://overviewer.org/textures/1.14 -O /root/.minecraft/versions/1.14/1.14.jar \
&& wget https://overviewer.org/textures/1.15 -O /root/.minecraft/versions/1.15/1.15.jar

COPY overviewer-cron /etc/cron.d/overviewer-cron

RUN chmod 600 /etc/cron.d/overviewer-cron

CMD ["cron", "-f"]