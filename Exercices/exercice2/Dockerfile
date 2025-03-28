FROM ubuntu:20.04

RUN apt-get update && apt-get install -y cron

RUN useradd -ms /bin/bash admin

RUN mkdir /scripts

RUN chown -R /scripts

COPY --chown=admin:admin ./scripts/. /scripts/.

COPY --chown=admin:admin cronjob /etc/cron.d/log-cron


RUN chmod +x /scripts/log-date.sh && chmod 0644 /etc/cron.d/log-cron

RUN touch /var/log/cron.log

RUN crontab /etc/cron.d/log-cron

USER admin

# A voir car le crontab ne démarre pas correctement
ENTRYPOINT  ["cron", "-f"]