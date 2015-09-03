FROM ubuntu:14.04
MAINTAINER Pasquale D'Agostino (@_elauqsap, blog.elauqsap.com)

USER root
RUN apt-get update
RUN apt-get install -q -y language-pack-en
RUN update-locale LANG=en_US.UTF-8
RUN apt-get install -q -y python-pip \
  python-dev \
  libffi-dev \
  libssl-dev \
  libxml2-dev \
  libxslt1-dev
RUN pip install mitmproxy

RUN groupadd -r nonroot && \
  useradd -r -g nonroot -d /home/nonroot -s /sbin/nologin -c "Nonroot User" nonroot && \
  mkdir /home/nonroot && \
  chown -R nonroot:nonroot /home/nonroot

USER nonroot
WORKDIR /home/nonroot
ENV LANG en_US.UTF-8

# Expose the default port
EXPOSE 8080

# Set default container command
ENTRYPOINT ["/usr/local/bin/mitmproxy"]
