FROM debian

ENV TS3SERVER_LICENSE=accept

WORKDIR /home/teamspeak

EXPOSE 9987/udp 10011 30033

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y bzip2 && \
    apt-get install -y wget && \
    wget http://dl.4players.de/ts/releases/3.5.1/teamspeak3-server_linux_amd64-3.5.1.tar.bz2 && \
    tar -xvjf teamspeak3-server_linux_amd64-3.5.1.tar.bz2

WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT sh ./ts3server_minimal_runscript.sh

# build :
# docker build -t image_tag folder

# run :
# docker run --rm -d --name="teamspeak_server" -p "9987:9987/udp" -p 10011:10011 -p 30033:30033 image_tag

# maintain :
# docker exec -ti container_name /bin/bash
