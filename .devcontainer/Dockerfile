FROM ghcr.io/cse-labs/k3d@sha256:86b1e13d1619b0b0b5ce4e94f7cc553ea504f559c31c52e396733a3a9918f247

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
