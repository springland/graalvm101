# Graalvm exercise project

## Setup Graalvm

1. Download Graalvm JDK 21
2. Follow [Windows installation](https://www.graalvm.org/latest/docs/getting-started/windows/) to install Graalvm
3. set java_home and path to Graalvm JDK 21 home 

## Build Spring Boot project
1. [Spring Boot build](https://docs.spring.io/spring-boot/docs/current/reference/html/native-image.html#native-image.developing-your-first-application.native-build-tools)

### Build native image   
mvnw -Pnative native:compile

target/graalvm101.exe

### Build Docker image
updated to use
<configuration>
    <!-- configure plugin here -->
        <image>
            <builder>paketobuildpacks/builder-jammy-base</builder>
        </image>
</configuration>

start docker

mvnw -Pnative spring-boot:build-image

docker run --rm -p 8080:8080 graalvm101:0.0.1-SNAPSHOT
