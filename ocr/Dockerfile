FROM debian:latest

RUN apt update &&  \
    apt install -y openssh-server &&  \
    rm -rf /var/lib/apt/lists/*

RUN mkdir -p /var/run/sshd

COPY authorized_keys /root/.ssh/authorized_keys
RUN chmod 700 /root/.ssh && chmod 600 /root/.ssh/authorized_keys

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
