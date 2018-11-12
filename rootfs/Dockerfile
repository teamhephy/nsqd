FROM nsqio/nsq:v1.1.0

RUN mkdir -p /opt/nsq/data \
    && adduser \
       -s /bin/sh \
       -D  \
       -h /opt/nsq \
       nsq \
       nsq

ADD https://github.com/stedolan/jq/releases/download/jq-1.6/jq-linux64 /usr/bin/jq

COPY . /
RUN chown -R nsq:nsq /opt/nsq
USER nsq
WORKDIR /
