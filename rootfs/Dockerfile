FROM quay.io/deis/base:v0.3.6

RUN adduser --system \
      --shell /bin/bash \
      --disabled-password \
      --home /opt/nsq \
      --group \
      nsq \
    && curl -Ls https://github.com/stedolan/jq/releases/download/jq-1.5/jq-linux64 > /usr/bin/jq \
    && chmod +x /usr/bin/jq \
    && curl -sL https://github.com/nsqio/nsq/releases/download/v1.0.0-compat/nsq-1.0.0-compat.linux-amd64.go1.8.tar.gz | tar xz \
    && mv /nsq-1.0.0-compat.linux-amd64.go1.8/bin/* /bin \
    && rm -r /nsq-1.0.0-compat.linux-amd64.go1.8 \
    && mkdir /opt/nsq/data

COPY . /
RUN chown -R nsq:nsq /opt/nsq
USER nsq
WORKDIR /opt/nsq/data
