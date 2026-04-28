FROM maven AS builder
WORKDIR /app
COPY . .
RUN mvn verify

FROM eclipse-temurin:8-jre
WORKDIR /app
COPY --from=builder /app/target/words.jar ./target/words.jar
COPY --from=builder /app/target/dependency ./target/dependency
CMD ["java", "-jar", "./target/words.jar"]