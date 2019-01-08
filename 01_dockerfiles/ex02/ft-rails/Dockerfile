FROM ruby

RUN apt-get update -y && apt-get install -y \
    build-essential \
    nodejs \
    sqlite3


ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app
ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

# build :
# docker build -t ft-rails:on-build /path/ft_rails/ -t image_tag
