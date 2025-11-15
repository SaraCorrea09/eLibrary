FROM jenkins/jenkins:lts

USER root

# Instalar Docker dentro del contenedor Jenkins
RUN apt-get update && \
    apt-get install -y docker.io && \
    usermod -aG docker jenkins

# Permitir acceso al socket docker
RUN chmod 666 /var/run/docker.sock

USER jenkins
