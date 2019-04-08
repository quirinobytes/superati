FROM quirinobytes/jenkins-slave-k8s

USER root

WORKDIR /usr/src/app

ENV PATH=/bin:/usr/bin:/usr/local/bin

# Add docker client

COPY . .
COPY docker/kube_config_cluster.yml ./

RUN npm install

VOLUME /var/lib/docker

EXPOSE 8080
ENTRYPOINT ["node app.js"]
