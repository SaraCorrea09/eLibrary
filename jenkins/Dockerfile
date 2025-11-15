FROM jenkins/jenkins:lts

USER root

# Instalar Docker dentro del contenedor para que Jenkins pueda usar Docker
RUN apt-get update && \
    apt-get install -y docker.io docker-compose && \
    apt-get clean

# Dar permisos al usuario jenkins
RUN usermod -aG docker jenkins

USER jenkins
