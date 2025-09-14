FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y openssh-server net-tools vim sudo nano tightvncserver\
    && rm -rf /var/lib/apt/lists/*

RUN useradd -m -s /bin/bash user && \
    echo "user:123456" | chpasswd && \
    adduser user sudo

RUN mkdir /var/run/sshd

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]