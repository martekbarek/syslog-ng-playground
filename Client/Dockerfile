FROM ubuntu

RUN apt-get update && apt-get install -y sudo syslog-ng lsof;

RUN	sed -i 's/^#\(SYSLOGNG_OPTS="--no-caps"\)/\1/g' /etc/default/syslog-ng

RUN sed -i "1s/.*/@version: 3.35/" /etc/syslog-ng/syslog-ng.conf

ADD ./client.conf /client.conf

RUN mv client.conf /etc/syslog-ng/conf.d/

RUN sudo /etc/init.d/syslog-ng restart