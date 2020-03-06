# alpine based git + make + docker + docker-compose build container
FROM spothero/baseline:latest

# must run start-docker before using docker
COPY start-docker /bin/

# install all the stuff
COPY install-dcind /bin/
RUN /bin/install-dcind
