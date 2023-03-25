FROM ubuntu:latest

RUN apt-get update                      && \
    apt-get install -y wget bash        && \
    apt-get clean

RUN mkdir /opt/cloudflared

RUN wget https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64 -O /opt/cloudflared/cloudflared

RUN wget https://raw.githubusercontent.com/Aequinoxio/DockerFileAndOtherThings/a9503c06d9b61fbad92bac21571551fb0ea539c3/cloudflare-dnssec/cloudflared.sh -O /opt/cloudflared/cloudflared.sh

# RUN echo "/opt/cloudflared/cloudflared proxy-dns --address 0.0.0.0 --port 54 --upstream https://1.1.1.1/.well-known/dns-query --upstream https://1.0.0.1/.well-known/dns-query" > /opt/cloudflared/cloudflared.sh

RUN chmod 755 /opt/cloudflared/cloudflared.sh
RUN chmod 755 /opt/cloudflared/cloudflared

EXPOSE 54

# CMD ["/bin/bash","/opt/cloudflared/cloudflared.sh"]
CMD ["/bin/bash","/bin/bash"]
