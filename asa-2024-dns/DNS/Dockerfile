FROM ubuntu:latest

RUN apt update -y

RUN apt update -y

RUN apt install bind9 bind9-utils dnsutils -y

COPY aristeu.asa.br /etc/bind
COPY named.conf.local /etc/bind

#Doors
EXPOSE 53/tcp
EXPOSE 53/udp
EXPOSE 953/tcp

CMD ["/usr/sbin/named","-g","-c", "/etc/bind/named.conf","-u","bind"]
