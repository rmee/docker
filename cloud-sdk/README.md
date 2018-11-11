# cloud-sdk

Tooling to access various cloud environments.

- kubectl
- helm
- Gradle
- Java
- google cloud sdk
- google cloud sql proxy
- more to follow

## Steps to publish

docker build cloud-sdk -t remmeier/cloud-sdk:0.1.2
docker login
docker push remmeier/cloud-sdk:0.1.2