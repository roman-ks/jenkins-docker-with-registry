FROM docker:dind
USER root
RUN mkdir /etc/docker
RUN echo "{\"insecure-registries\" : [ \"myregistry:5000\" ]}" > /etc/docker/daemon.json