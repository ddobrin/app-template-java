# Commands to build the generated project

Build an App Image
```shell
# JVM app
./mvnw clean package -Pjvm

# Native app
./mvnw clean package -Pnative
```

Build a Docker Image using Cloud Native Buildpacks
```shell
# JVM-based container image
./mvnw clean package -Pjvm-image

# Native app-based container image
./mvnw clean package -Pnative-image
```

Run the Docker images before deployment
```shell
# Run VM-based container image
docker run -p 8080:8080 modernapp-jvm

# Run Native app-based container image
docker run -p 8080:8080 modernapp-native
```

Test and healthcheck commands
```shell
# test controller
http :8080/hello

# Health actuator
http :8080/actuator/health

# Startup actuator
http :8080/actuator/startup