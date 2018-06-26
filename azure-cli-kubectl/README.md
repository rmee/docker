# Collection of Docker images

- azure-cli-kubectl: Azure CLI bundled with Kubernetes to support aks commands

## Steps to publish

docker build azure-cli-kubectl -t remmeier/azure-cli-kubectl:2.0.38
docker login
docker push remmeier/azure-cli-kubectl:2.0.38