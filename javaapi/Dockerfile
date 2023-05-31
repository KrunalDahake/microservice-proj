FROM openjdk:8 as build_image
WORKDIR /usr/src/app
COPY ./ ./
RUN apt update && apt install maven -y
RUN  mvn install -DskipTests

FROM openjdk:8 
WORKDIR /usr/src/app
COPY --from=build_image /usr/src/app/target/book-work-0.0.1-SNAPSHOT.jar  ./book-work-0.0.1.jar
ENTRYPOINT ["java","-jar","book-work-0.0.1.jar"]

