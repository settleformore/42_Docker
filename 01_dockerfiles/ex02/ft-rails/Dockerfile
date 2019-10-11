# ruby apps are great because they seamlessly created a connection between a front and a end and build their own databases
# the commands for scaffold or editing a db is the rake commands so its important to set them up
# bundler is also important because the install bundle or just bundle command


# this needs to be run before the main Dockerfile submission 
# run with docker build -t ft-rails:on-build .


FROM ruby:2.5.1

RUN apt-get update && apt-get upgrade -y nodejs && \
    gem install rails && \
	gem install bundler && \
    gem install nodejs-rails && \
    gem update --system

ONBUILD WORKDIR /opt

ONBUILD ADD app /opt/app
ONBUILD WORKDIR /opt/app
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

