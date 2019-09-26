# ruby apps are great because they seamlessly created a connection between a front and a end and build their own databases
# the commands for scaffold or editing a db is the rake commands so its important to set them up
# bundler is also important because the install bundle or just bundle command


# this needs to be run before the main Dockerfile submission 
# run with docker build -t ft-rails:on-build .


FROM ruby:2.5.1
# RUN cd opts/
RUN apt-get update -y && apt-get upgrade -y && apt-get install -y \
	nodejs && \
	gem install rails && \
	gem install bundler
RUN rails new app

ONBUILD RUN cd app && bundle install && \
			rake db:migrate && \
			rake db:setup
WORKDIR	/app

