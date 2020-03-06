# ubuntu based docker / docker-compose build container
FROM spothero/dcind-alpine:latest as dcind
FROM ubuntu:20.04

COPY --from=dcind /bin/start-docker /bin/
COPY install-dcind /bin/
RUN /bin/install-dcind

# yq
RUN apt install wget && \
    wget -O /bin/yq https://github.com/mikefarah/yq/releases/download/2.4.1/yq_linux_amd64 && \
    chmod +x /bin/yq
