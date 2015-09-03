FROM ubuntu:14.04
MAINTAINER Pasquale D'Agostino (@_elauqsap, blog.elauqsap.com)

USER root
# Update Base System
RUN apt-get update && apt-get -y upgrade \
      && apt-get install -y language-pack-en \
      && locale-gen en_US.UTF-8 \
      && dpkg-reconfigure locales

# Install Basic Packages
RUN apt-get install -y build-essential \
  software-properties-common \
  wget curl git man unzip tmux \
  colord zsh git-core zlib1g-dev \
  libssl-dev libreadline-dev \
  libyaml-dev libsqlite3-dev \
  sqlite3 libxml2-dev libxslt1-dev \
  libcurl4-openssl-dev python-software-properties \
  libffi-dev

CMD ["zsh"]
