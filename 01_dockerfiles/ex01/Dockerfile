# From a debian image you will add the appropriate sources to create a TeamSpeak
# server, that will launch along with your container. It will be deemed valid if at least
# one user can connect to it and engage in a normal discussion (no far-fetched setup), so
# be sure to create your Dockerfile with the right options. Your program should get the
# sources when it builds, they cannot be in your repository

# docker build -t ex01 .
# docker run --rm -it -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ex01

# to check one can log into the teamspeak gui and in the connections put the ip address of Char and 9987 as the port
# ex : 192.168.99.100:9987

FROM debian 

ENV TS3SERVER_LICENSE=accept

WORKDIR /home/teamspeak

RUN apt-get update && apt-get upgrade -y

RUN apt-get install -y wget bzip2

RUN wget https://files.teamspeak-services.com/releases/server/3.7.1/teamspeak3-server_linux_amd64-3.7.1.tar.bz2

RUN tar -xvf teamspeak3-server_linux_amd64-3.7.1.tar.bz2

EXPOSE 9987/udp 10011 30033

WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT sh ts3server_minimal_runscript.sh

#--Notes--
# Teamspeak is a voice communcation software for online services. Used for business and personal services
