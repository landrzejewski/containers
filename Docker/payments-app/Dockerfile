FROM amazoncorretto:17-alpine
COPY shop-1.0-SNAPSHOT.jar /shop-1.0-SNAPSHOT.jar
ENV SPRING_DATASOURCE_URL=jdbc:postgresql://postgres:5432/payments
EXPOSE 8000
ENTRYPOINT ["java", "-jar", "shop-1.0-SNAPSHOT.jar"]

