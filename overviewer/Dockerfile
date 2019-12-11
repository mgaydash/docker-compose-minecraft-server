FROM ubuntu:18.04

RUN apt-get update \
&& apt-get install -y wget apt-transport-https gnupg2 cron \
&& echo 'deb https://overviewer.org/debian ./' >> /etc/apt/sources.list \
&& wget -O - https://overviewer.org/debian/overviewer.gpg.asc | apt-key add - \
&& apt-get update \
&& apt-get install -y minecraft-overviewer

CMD ["cron", "-f"]