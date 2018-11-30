FROM ubuntu:18.04

RUN apt update && apt install -q -y vim git openssh-server gnupg2
RUN echo "root:15rabbits" | chpasswd
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF \
  && echo "deb https://download.mono-project.com/repo/ubuntu stable-bionic main" | tee /etc/apt/sources.list.d/mono-official-stable.list \
  && apt update \
  && apt install -q -y mono-xbuild \
    mono-utils \
    mono-runtime \
    mono-tools-devel \
    mono-llvm-dev \
    mono-csharp-shell \
    mono-4.0-service \
    mono-complete \
    mono-devel

EXPOSE 22

COPY docker-entrypoint.sh /bin/docker-entrypoint.sh
CMD /bin/bash /bin/docker-entrypoint.sh
