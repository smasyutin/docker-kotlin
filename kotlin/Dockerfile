FROM openjdk:14

ENV KOTLIN_HOME=/usr/kotlinc
ENV PATH=$KOTLIN_HOME/bin:$PATH

RUN yum install -y unzip; \
curl -fL -o kotlin.zip https://github.com/JetBrains/kotlin/releases/download/v1.3.71/kotlin-compiler-1.3.71.zip; \
unzip /kotlin.zip -d /usr/; yum remove -y unzip; yum clean -y all; \
rm /kotlin.zip; kotlinc -version

CMD ["kotlinc"]