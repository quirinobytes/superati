FROM quirinobytes/jenkins-slave-k8s

USER root
WORKDIR /app

ENV PATH=/bin:/usr/bin:/usr/local/bin
ENV APP_NAME=www.superati.com.br

# Add docker client

COPY . ./
COPY kube_config_cluster.yml ./

RUN npm install
VOLUME /var/lib/docker
//VOLUME /var/run/docker.sock

EXPOSE 1010
ENTRYPOINT ["/usr/bin/nodejs","app.js"]
