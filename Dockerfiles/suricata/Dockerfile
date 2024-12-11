FROM ubuntu:22.04

RUN apt update && apt upgrade -y && \
    apt install -y software-properties-common && \
    add-apt-repository ppa:oisf/suricata-stable && \
    apt install -y suricata jq cron multitail

COPY update-rules /etc/cron.d/update-rules

RUN chmod 0644 /etc/cron.d/update-rules && \
    touch /var/log/cron.log

CMD cron && tail -f /var/log/cron.log
