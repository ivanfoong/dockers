FROM debian:jessie
MAINTAINER Ivan Foong "vonze21@gmail.com"

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y ruby ruby-dev build-essential nodejs python-pygments && gem install jekyll bundler therubyracer rouge --no-ri --no-rdoc && apt-get remove --purge -y build-essential ruby-dev && apt-get autoclean && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ADD jekyll-serve.sh /usr/local/bin/jekyll-serve
RUN chmod +x /usr/local/bin/jekyll-serve

RUN mkdir -p /home/jekyll/source

EXPOSE 4000
VOLUME ["/home/jekyll/source"]
WORKDIR /home/jekyll/source
CMD ["jekyll-serve"]

