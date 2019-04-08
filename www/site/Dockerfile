FROM quirinobytes/jenkins-k8s-nodejs

USER root

WORKDIR /usr/src/app

# Add docker client

COPY . .
COPY docker/kube_config_cluster.yml ./

RUN npm install

VOLUME /var/lib/docker

EXPOSE 8080
ENTRYPOINT ["node app.js"]
