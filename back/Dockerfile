FROM openjdk:8
# Instalar git para clonar repo
RUN apt-get update && apt-get install git -y
# Clonar repo
RUN git clone https://github.com/kuroibatusai/ms-iclab
# Construir aplicación usando el Gradle Wrapper
RUN cd ms-iclab && ls && ./gradlew clean build
# Comando a ejecutar cuando inicie el contenedor
CMD ["java", "-jar", "ms-iclab/build/libs/DevOpsUsach2020-0.0.1.jar"]