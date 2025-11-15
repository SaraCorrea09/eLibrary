FROM jenkins/jenkins:lts

USER root

# Instalar dependencias necesarias
RUN apt-get update && \
    apt-get install -y ca-certificates curl gnupg lsb-release

# Instalar Docker Engine dentro del contenedor
RUN mkdir -m 0755 -p /etc/apt/keyrings && \
    curl -fsSL https://download.docker.com/linux/debian/gpg \
      | gpg --dearmor -o /etc/apt/keyrings/docker.gpg && \
    echo \
      "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
      https://download.docker.com/linux/debian \
      $(lsb_release -cs) stable" \
      > /etc/apt/sources.list.d/docker.list && \
    apt-get update && \
    apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# Dar permisos al socket Docker y añadir jenkins al grupo docker
RUN usermod -aG docker jenkins && \
    chmod 666 /var/run/docker.sock

USER jenkins
