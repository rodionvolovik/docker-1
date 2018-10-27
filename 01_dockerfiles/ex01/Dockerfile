FROM debian

ENV TSV=3.0.13.8

RUN apt-get -y update && \
	apt-get -y upgrade && \
	apt-get -y install curl && \
	apt-get -y install bzip2 && \
	apt-get -y install wget

RUN wget http://dl.4players.de/ts/releases/${TSV}/teamspeak3-server_linux_amd64-${TSV}.tar.bz2

RUN tar jxf teamspeak3-server_linux_amd64-$TSV.tar.bz2 && \
	mv teamspeak3-server_linux_amd64 /opt/teamspeak && \
    rm teamspeak3-server_linux_amd64-$TSV.tar.bz2

EXPOSE 9987/udp 10011 30033

CMD ["/opt/teamspeak/ts3server_minimal_runscript.sh"]

#docker run -d -it -p 9987:9987/udp -p 10011:10011 -p 30033:30033 --name=TS -e TS3SERVER_LICENSE=accept #
