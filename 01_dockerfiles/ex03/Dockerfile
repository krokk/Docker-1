FROM ubuntu

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y wget openssh-server ca-certificates postfix

RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh && chmod 777 script.deb.sh && ./script.deb.sh && apt-get install -y gitlab-ce

RUN apt-get install -y tzdata

EXPOSE 443 80 22

ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && tail -f /dev/null

# build :
# docker build folder -t image_tag

# run :
# docker run -it --rm -p 8080:80 -p 2222:22 -p 4433:443 --privileged image_tag
