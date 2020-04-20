FROM adoptopenjdk:14-hotspot

ARG KOTLIN_VERSION=1.3.72

ENV KOTLIN_HOME=/usr/kotlinc
ENV PATH=$KOTLIN_HOME/bin:$PATH

RUN apt-get update -y; apt-get install -y unzip; \
curl -fL -o kotlin.zip https://github.com/JetBrains/kotlin/releases/download/v$KOTLIN_VERSION/kotlin-compiler-$KOTLIN_VERSION.zip; \
unzip /kotlin.zip -d /usr/; apt-get remove -y unzip; apt-get autoclean -y all; \
rm /kotlin.zip; kotlinc -version

CMD ["kotlinc"]