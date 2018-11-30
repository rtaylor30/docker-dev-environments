FROM ubuntu:18.04

RUN apt update && apt install -q -y vim git openssh-server
RUN echo  -n 15rabbits | passwd root --stdin

EXPOSE 22

COPY docker-entrypoint.sh /bin/docker-entrypoint.sh
CMD /bin/bash /bin/docker-entrypoint.sh
