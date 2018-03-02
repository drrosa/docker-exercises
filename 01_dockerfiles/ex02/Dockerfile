FROM ruby
RUN apt-get update -y \
	&& apt-get install nodejs -y \
	&& gem install rails
EXPOSE 3000
ONBUILD COPY app/ /opt/app
WORKDIR /opt/app
ONBUILD RUN bundle install \
			&& rake db:migrate \
			&& rake db:setup \
			&& rake db:seed
