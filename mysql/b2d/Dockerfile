FROM mysql:5.7.11
MAINTAINER Sergey Gernyak "sergeg1990@gmail.com"

# This need to stay the same for script to work
ENV MYSQL_USER mysql

# Copy local run script into image
COPY ./local-run.sh /

RUN chmod 755 /local-run.sh

# Set entrypoint command to local run script which solves permissions issue
ENTRYPOINT ["/local-run.sh"]
