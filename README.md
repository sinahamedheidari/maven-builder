# Maven Builder Docker Image
This image is used to easily build maven project with maven 3.6 and Java 11 and optionally upload to a FTP server.

## How to build the Image
```
git clone https://github.com/sinahamedheidari/maven-builder
cd java-11
docker build -t maven-builder .
```
Then you can use the maven builder container manually or in ci/cd tools such as Jenkins.