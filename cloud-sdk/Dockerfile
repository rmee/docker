FROM google/cloud-sdk:224.0.0 as build

ENV HELM_VERSION=v2.11.0
ENV HELM_FILENAME=helm-${HELM_VERSION}-linux-amd64.tar.gz

ENV GRADLE_VERSION=4.10.2
ENV GRADLE_FILENAME=gradle-${GRADLE_VERSION}-all.zip

WORKDIR /


RUN apt-get -qqy update && apt-get install -qqy unzip


RUN curl -L https://services.gradle.org/distributions/${GRADLE_FILENAME} > ${GRADLE_FILENAME} && \
    unzip -d /opt ${GRADLE_FILENAME} && \
    mv /opt/gradle-${GRADLE_VERSION}/ /opt/gradle/ && \
    chmod a+x /opt/gradle/bin/gradle && \
    rm -f ${GRADLE_FILENAME}


RUN curl -L http://storage.googleapis.com/kubernetes-helm/${HELM_FILENAME} > ${HELM_FILENAME} && \
    tar zxv -C /tmp -f ${HELM_FILENAME} && \
    chmod a+x /tmp/linux-amd64/helm && \
    rm -f ${HELM_FILENAME}



FROM google/cloud-sdk:224.0.0
COPY --from=build /tmp/linux-amd64/helm /bin/helm
COPY --from=build /opt/gradle /opt/gradle

RUN apt-get -qqy update && apt-get install -qqy \
        openjdk-8-jre
