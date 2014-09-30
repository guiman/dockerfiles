FROM ubuntu:precise

MAINTAINER Alvaro F. Lara <alvaro.lara@alliants.com>

RUN apt-get update && apt-get install -y build-essential wget

# Install ruby-install
RUN wget -O ruby-install-0.4.3.tar.gz https://github.com/postmodern/ruby-install/archive/v0.4.3.tar.gz --no-check-certificate; \
  tar -xzvf ruby-install-0.4.3.tar.gz; cd ruby-install-0.4.3/; make install; cd; rm -Rf ruby-install-0.4.3 ruby-install-0.4.3.tar.gz;

ADD .ruby-version .

# Install ruby
RUN ruby-install -i /usr/local/ ruby $(cat .ruby-version)

# Creating the user
useradd -m -s /bin/bash app

ONBUILD RUN gem install bundler
ONBUILD ADD . /home/app/
ONBUILD WORKDIR /home/app
ONBUILD ENV HOME /home/app
