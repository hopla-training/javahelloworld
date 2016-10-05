1. In the javahelloworld folder, create a Dockerfile.javahelloworld

2. Use java:7 as your base image. This image contains the JDK needed to build and run our application
FROM java:7

3. Copy your source file into the container root folder
COPY HelloWorld.java /

4. Add an instruction to compile your code
RUN javac HelloWorld.java

5. Add an instruction to run your program when running the container
ENTRYPOINT ["java", "HelloWorld"]

6. Build the image

7. Run a container from the image and observe the output




docker run --rm javahelloworld

docker run --rm javahelloworld-alpine


docker build -t javahelloworld -f Dockerfile.javahelloworld .

docker build -t javahelloworld-alpine -f Dockerfile.javahelloworld-alpine .

docker run -ti --rm -v $(pwd)/HelloWorld.java:/HelloWorld.java -v $(pwd)/tmp:/tmp jdk7 javac /HelloWorld.java -d /tmp


docker images|grep javahelloworld

javahelloworld             latest              10f25bff5fb9        6 minutes ago       584.6 MB

javahelloworld-alpine      latest              786b879771a8        6 minutes ago       143.7 MB

