FROM ruby
RUN apt-get update -y \
	&& apt-get install libgmp-dev libgsl0-dev nodejs -y \
	&& gem install bundler rails
EXPOSE 3000
ONBUILD COPY app/ /opt/app
ONBUILD WORKDIR /opt/app
ONBUILD RUN bundle install \
			&& rake db:migrate \
			rake db:seed
