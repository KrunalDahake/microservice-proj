FROM openjdk:8 as build_image
WORKDIR /usr/src/app
COPY ./ ./booksapi
RUN apt update && apt install maven -y
RUN cd booksapi && mvn install

FROM openjdk:8 
COPY --from=build_image /usr/src/app/booksapi/target/book-work-0.0.1-SNAPSHOT.jar  /usr/src/app/book-work.jar
ENTRYPOINT ["java","-jar","book-work.jar"]

