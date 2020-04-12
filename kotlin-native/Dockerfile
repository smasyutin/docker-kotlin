FROM adoptopenjdk:14-hotspot

ENV KOTLIN_HOME=/usr/kotlinc
ENV PATH=$KOTLIN_HOME/bin:$PATH

RUN curl -fL -o kotlin.tgz https://github.com/JetBrains/kotlin/releases/download/v1.3.71/kotlin-native-linux-1.3.71.tar.gz; \
mkdir -p "$KOTLIN_HOME"; tar --extract --file /kotlin.tgz --directory "$KOTLIN_HOME" --strip-components 1; \
rm /kotlin.tgz; \
echo "fun main() { println() }" > pull_compiler_dependencies.kt; \
kotlinc pull_compiler_dependencies.kt -o remove_me; \
rm pull_compiler_dependencies.kt remove_me.kexe

CMD ["kotlinc"]