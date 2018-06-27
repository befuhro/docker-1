FROM debian

#accept teamspeak license
ENV	TS3SERVER_LICENSE=accept

#open port necessary for teamspeak
EXPOSE 9987
EXPOSE 30033
EXPOSE 10011

RUN apt-get update && \
	apt-get upgrade -y && \
	apt-get install -y wget bzip2 && \
	useradd -m ts3 && \
	cd /home/ts3 && \
	wget http://dl.4players.de/ts/releases/3.2.0/teamspeak3-server_linux_amd64-3.2.0.tar.bz2 && \
	tar -xvf teamspeak3-server_linux_amd64-3.2.0.tar.bz2 && \
	rm teamspeak3-server_linux_amd64-3.2.0.tar.bz2
COPY ts3server.ini /home/ts3/teamspeak3-server_linux_amd64
WORKDIR /home/ts3/teamspeak3-server_linux_amd64
CMD ["sh", "ts3server_minimal_runscript.sh"]
# the image must be run with the following options:
# -it -p 9987:9987/udp -p 30033:30033 -p 10011:10011
