FROM debian:latest
RUN apt-get update \
	&& apt-get install -y wget \
	&& apt-get install bzip2 \
	&& useradd -d /teamspeak teamspeak \
	&& wget http://dl.4players.de/ts/releases/3.1.0/teamspeak3-server_linux_amd64-3.1.0.tar.bz2 -O teamspeak3.bz2 \
	&& tar -xvf teamspeak3.bz2
EXPOSE 9987/udp 30033 10011 41144
RUN su teamspeak -c "/teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh createinfile=1 license_accepted=1"
