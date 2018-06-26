FROM microsoft/azure-cli:2.0.38

LABEL authors="Remo Meier <remo.meier.ch@gmail.com>"

ENV KUBERNETES_VERSION=1.10.0
RUN wget https://storage.googleapis.com/kubernetes-release/release/v${KUBERNETES_VERSION}/bin/linux/amd64/kubectl -qO /usr/local/bin/kubectl
RUN chmod +x /usr/local/bin/kubectl