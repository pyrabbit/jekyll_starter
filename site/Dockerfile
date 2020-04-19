FROM ruby:2.7

RUN apt-get install bash
# throw errors if Gemfile has been modified since Gemfile.lock
RUN bundle config --global frozen 1

WORKDIR /usr/src/app

COPY Gemfile Gemfile.lock    ./
RUN bundle install

COPY . .
COPY entrypoint.sh /usr/local/bin

RUN chmod +x /usr/local/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]
