FROM jenkinsci/jnlp-slave

USER root

WORKDIR /opt

# Add docker client
ENV DOCKER_VERION=1.12.5
ENV KUBECONFIG=kube_config_cluster.yml
ENV PATH=$PATH:/bin:/usr/bin:/usr/bin/local

RUN wget https://get.docker.com/builds/Linux/x86_64/docker-${DOCKER_VERION}.tgz
RUN tar -zxvf docker-${DOCKER_VERION}.tgz
RUN cp docker/docker /usr/bin/
RUN rm -rf /opt/docker*

# Add kubectl client
ENV KUBECTL_VERSION 1.5.1
RUN wget https://storage.googleapis.com/kubernetes-release/release/v1.5.1/bin/linux/amd64/kubectl
RUN chmod +x kubectl
RUN mv kubectl /usr/bin/

RUN apt-get update

# node.js
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash -
RUN apt-get -y install gcc g++ make
RUN apt-get install -y nodejs

COPY kube_config_cluster.yml ./

# Add python virtualenv and libs
RUN apt-get install -y python-pip python-dev libxml2-dev libxslt1-dev zlib1g-dev junit bc
RUN pip install virtualenv

VOLUME /var/lib/docker

ENTRYPOINT ["jenkins-slave"]
