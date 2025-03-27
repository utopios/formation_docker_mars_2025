FROM ubuntu:20.04

RUN apt-get update && apt-get install -y cron

RUN mkdir /scripts

COPY ./scripts/. /scripts/.

COPY cronjob /etc/cron.d/log-cron

RUN chmod +x /scripts/log-date.sh && chmod 0644 /etc/cron.d/log-cron

RUN touch /var/log/cron.log

RUN crontab /etc/cron.d/log-cron

CMD  ["cron", "-f"]