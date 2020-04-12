FROM adoptopenjdk:14-hotspot

ENV KOTLIN_HOME=/usr/kotlinc
ENV PATH=$KOTLIN_HOME/bin:$PATH

RUN apt-get update -y; apt-get install -y unzip; \
curl -fL -o kotlin.zip https://github.com/JetBrains/kotlin/releases/download/v1.3.71/kotlin-compiler-1.3.71.zip; \
unzip /kotlin.zip -d /usr/; apt-get remove -y unzip; apt-get autoclean -y all; \
rm /kotlin.zip; kotlinc -version

CMD ["kotlinc"]