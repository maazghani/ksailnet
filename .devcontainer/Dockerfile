FROM ghcr.io/cse-labs/k3d:latest

# some images require specific values
ARG USERNAME=vscode

# install kubecolor
RUN apt-get update && \
    apt-get install -y wget && \
    wget -O /tmp/kubecolor.deb https://kubecolor.github.io/packages/deb/pool/main/k/kubecolor/kubecolor_0.5.1_amd64.deb && \
    dpkg -i /tmp/kubecolor.deb && \
    rm -rf /tmp/kubecolor.deb && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# log the docker build start event
RUN echo "$(date +'%Y-%m-%d %H:%M:%S')    docker build start" >> /home/$USERNAME/status

RUN chown -R $USERNAME:$USERNAME /home/$USERNAME

# log the docker build complete
RUN echo "$(date +'%Y-%m-%d %H:%M:%S')    docker build complete" >> /home/$USERNAME/status
