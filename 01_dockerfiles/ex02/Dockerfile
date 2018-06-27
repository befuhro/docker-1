FROM ruby:jessie

RUN apt-get update && apt-get install nodejs -y && \
	gem install rails

ONBUILD COPY app/ /opt/app

ONBUILD RUN bundle install && \
	rake db:migrate && \
	rake db:setup && \
	rake db:seed

WORKDIR /opt/app
