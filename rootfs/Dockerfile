FROM quay.io/deis/base:v0.3.6

RUN adduser --system \
      --shell /bin/bash \
      --disabled-password \
      --home /opt/nsq \
      --group \
      nsq \
    && curl -Ls https://github.com/stedolan/jq/releases/download/jq-1.5/jq-linux64 > /usr/bin/jq \
    && chmod +x /usr/bin/jq \
    && curl -sL https://github.com/nsqio/nsq/releases/download/v1.1.0/nsq-1.1.0.linux-amd64.go1.10.3.tar.gz | tar xz \
    && mv /nsq-1.1.0.linux-amd64.go1.10.3/bin/* /bin \
    && rm -r /nsq-1.1.0.linux-amd64.go1.10.3 \
    && mkdir /opt/nsq/data

COPY . /
RUN chown -R nsq:nsq /opt/nsq
USER nsq
WORKDIR /
