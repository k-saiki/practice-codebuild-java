FROM ubuntu:16.04

ENV JAVA_PACKAGE_NAME=openjdk-8-jdk \
    GRADLE_VERSION=4.2.1

RUN set -ex \
    && apt update \
    && apt install -y curl wget unzip zip ${JAVA_PACKAGE_NAME} \
    && apt clean \
    # install gradle
    && mkdir -p /usr/src/gradle \
    && wget "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" -O /usr/src/gradle/gradle-${GRADLE_VERSION}-bin.zip \
    && unzip /usr/src/gradle/gradle-${GRADLE_VERSION}-bin.zip -d /usr/local \
    && ln -s /usr/local/gradle-${GRADLE_VERSION}/bin/gradle /usr/bin/gradle \
    && rm -rf /usr/src/gradle \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*