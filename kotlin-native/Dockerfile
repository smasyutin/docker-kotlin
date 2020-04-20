FROM adoptopenjdk:14-hotspot

ARG KOTLIN_VERSION=1.3.72

ENV KOTLIN_HOME=/usr/kotlinc
ENV PATH=$KOTLIN_HOME/bin:$PATH

RUN curl -fL -o kotlin.tgz https://github.com/JetBrains/kotlin/releases/download/v$KOTLIN_VERSION/kotlin-native-linux-$KOTLIN_VERSION.tar.gz; \
mkdir -p "$KOTLIN_HOME"; tar --extract --file /kotlin.tgz --directory "$KOTLIN_HOME" --strip-components 1; \
rm /kotlin.tgz; \
echo "fun main() { println() }" > pull_compiler_dependencies.kt; \
kotlinc pull_compiler_dependencies.kt -o remove_me; \
rm pull_compiler_dependencies.kt remove_me.kexe

CMD ["kotlinc"]