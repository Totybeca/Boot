# Drone api


## Requirements

The following are the steps to create a simple Spring Boot Project:

Step 1: Open the Spring initializr https://start.spring.io.

Step 2: Provide the Group and Artifact name. We have provided Group name com.javatpoint and Artifact spring-boot-example.

Step 3: Now click on the Generate button.

![image](https://user-images.githubusercontent.com/106770765/196445093-10239cb0-c0bd-43af-85ca-1e3eb225df80.png)

When we click on the Generate button, it starts packing the project in a .rar file and downloads the project.

Step 4: Extract the RAR file.

Step 5: Import the folder.

File -> Import -> Existing Maven Project -> Next -> Browse -> Select the project -> Finish

It takes some time to import the project. When the project imports successfully, we can see the project directory in the Package Explorer. The following image shows the project directory:
![image](https://user-images.githubusercontent.com/106770765/196445772-20b542d0-b280-4b9b-b8f0-1c934f833887.png)
SpringBootExampleApplication.java

package com.javatpoint.springbootexample;  
import org.springframework.boot.SpringApplication;  
import org.springframework.boot.autoconfigure.SpringBootApplication;  
@SpringBootApplication  
public class SpringBootExampleApplication   
{  
public static void main(String[] args)   
{  
SpringApplication.run(SpringBootExampleApplication.class, args);  
}  
}  
pom.xml

<?xml version="1.0" encoding="UTF-8"?>  
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">  
<modelVersion>4.0.0</modelVersion>  
<parent>  
<groupId>org.springframework.boot</groupId>  
<artifactId>spring-boot-starter-parent</artifactId>  
<version>2.2.2.BUILD-SNAPSHOT</version>  
<relativePath/> <!-- lookup parent from repository -->  
</parent>  
<groupId>com.javatpoint</groupId>  
<artifactId>spring-boot-example</artifactId>  
<version>0.0.1-SNAPSHOT</version>  
<name>spring-boot-example</name>  
<description>Demo project for Spring Boot</description>  
<properties>  
<java.version>1.8</java.version>  
</properties>  
<dependencies>  
<dependency>  
<groupId>org.springframework.boot</groupId>  
<artifactId>spring-boot-starter</artifactId>  
</dependency>  
<dependency>  
<groupId>org.springframework.boot</groupId>  
<artifactId>spring-boot-starter-test</artifactId>  
<scope>test</scope>  
<exclusions>  
<exclusion>  
<groupId>org.junit.vintage</groupId>  
<artifactId>junit-vintage-engine</artifactId>  
</exclusion>  
</exclusions>  
</dependency>  
</dependencies>  
<build>  
<plugins>  
<plugin>  
<groupId>org.springframework.boot</groupId>  
<artifactId>spring-boot-maven-plugin</artifactId>  
</plugin>  
</plugins>  
</build>  
<repositories>  
<repository>  
<id>spring-milestones</id>  
<name>Spring Milestones</name>  
<url>https://repo.spring.io/milestone</url>  
</repository>  
<repository>  
<id>spring-snapshots</id>  
<name>Spring Snapshots</name>  
<url>https://repo.spring.io/snapshot</url>  
<snapshots>  
<enabled>true</enabled>  
</snapshots>  
</repository>  
</repositories>  
<pluginRepositories>  
<pluginRepository>  
<id>spring-milestones</id>  
<name>Spring Milestones</name>  
<url>https://repo.spring.io/milestone</url>  
</pluginRepository>  
<pluginRepository>  
<id>spring-snapshots</id>  
<name>Spring Snapshots</name>  
<url>https://repo.spring.io/snapshot</url>  
<snapshots>  
<enabled>true</enabled>  
</snapshots>  
</pluginRepository>  
</pluginRepositories>  
</project>  
Step 6: Run the SpringBootExampleApplication.java file.
Right-click on the file -> Run As -> Java Applications

Creating Spring Boot Project
The following image shows the application runs successfully.

## Running the application locally

There are several ways to run a Spring Boot application on your local machine. One way is to execute the `main` method in the `de.codecentric.springbootsample.Application` class from your IDE.

Alternatively you can use the [Spring Boot Maven plugin](https://docs.spring.io/spring-boot/docs/current/reference/html/build-tool-plugins-maven-plugin.html) like so:

```shell
mvn spring-boot:run
```

## Deploying the application to OpenShift

The easiest way to deploy the sample application to OpenShift is to use the [OpenShift CLI](https://docs.openshift.org/latest/cli_reference/index.html):

```shell
oc new-app codecentric/springboot-maven3-centos~https://github.com/codecentric/springboot-sample-app
```

This will create:

* An ImageStream called "springboot-maven3-centos"
* An ImageStream called "springboot-sample-app"
* A BuildConfig called "springboot-sample-app"
* DeploymentConfig called "springboot-sample-app"
* Service called "springboot-sample-app"

If you want to access the app from outside your OpenShift installation, you have to expose the springboot-sample-app service:

```shell
oc expose springboot-sample-app --hostname=www.example.com
```

## Copyright
