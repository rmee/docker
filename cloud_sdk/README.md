# cloud-sdk

Tooling to access various cloud environments.

- kubectl
- helm
- Gradle
- Java
- google cloud sdk
- more to follow

## Steps to publish

docker build azure-cli-kubectl -t remmeier/cloud-sdk:0.1.0
docker login
docker push remmeier/cloud-sdk:0.1.0