FROM quirinobytes/jenkins-slave-k8s

USER root

WORKDIR /app

ENV PATH=/bin:/usr/bin:/usr/local/bin

# Add docker client

COPY . ./
RUN npm install

COPY kube_config_cluster.yml ./

RUN pwd
RUN ls -la
RUN whereis node
RUN ls /usr/bin


VOLUME /var/lib/docker

EXPOSE 1010
ENTRYPOINT ["/usr/bin/nodejs","app.js"]
