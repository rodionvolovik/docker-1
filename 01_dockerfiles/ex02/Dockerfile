FROM ruby:2.3.4

RUN apt-get -y update && \
	apt-get -y upgrade && \
	apt-get -y install nodejs
RUN gem install rails
RUN gem install bundle
RUN rails new server && cd server

EXPOSE 3000

ONBUILD COPY app/ /opt/app

ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:setup
ONBUILD RUN rake db:seed