# alpine based git + make + docker + docker-compose build container
FROM alpine

RUN apk add git bash make curl

# must run start-docker before using docker
COPY start-docker /bin/

# install all the stuff
COPY install-dcind /bin/
RUN /bin/install-dcind
