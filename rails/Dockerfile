FROM ruby:2.4.0
RUN mv /etc/apt/sources.list /etc/apt/sources.list.bak && \
    echo "deb http://mirrors.163.com/debian/ jessie main non-free contrib" >/etc/apt/sources.list && \
    echo "deb http://mirrors.163.com/debian/ jessie-proposed-updates main non-free contrib" >>/etc/apt/sources.list && \
    echo "deb-src http://mirrors.163.com/debian/ jessie main non-free contrib" >>/etc/apt/sources.list && \
    echo "deb-src http://mirrors.163.com/debian/ jessie-proposed-updates main non-free contrib" >>/etc/apt/sources.list
RUN apt-get update -qq && apt-get install -y build-essential libssl-dev git --fix-missing --no-install-recommends

# mysql
#RUN apt-get install -y libmysqlclient-dev

# postgres ?postgresql-client
RUN apt-get install -y libpq-dev

# nokogiri
#RUN apt-get install -y libxml2-dev libxslt1-dev

# minimagick
#RUN apt-get install -y imagemagick libbz2-dev libjpeg-dev libevent-dev libmagickcore-dev libffi-dev libglib2.0-dev zlib1g-dev libyaml-dev

# qt for capybara capybara-webkit
#RUN apt-get install -y qt5-default libqt5webkit5-dev gstreamer1.0-plugins-base gstreamer1.0-tools gstreamer1.0-x xvfb --fix-missing --no-install-recommends

# node js for coffee and sass
RUN curl -sL https://deb.nodesource.com/setup_7.x | bash -
RUN apt-get install -y nodejs

ENV APP_HOME /rails_apps
RUN mkdir $APP_HOME
WORKDIR $APP_HOME

#ADD Gemfile* $APP_HOME/
#RUN bundle install

# postgres 配置
#ENV DEV_DB_HOST db

# redis
ENV REDIS_HOST redis
ADD . $APP_HOME
