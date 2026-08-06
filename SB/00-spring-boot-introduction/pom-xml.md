=====================================
POM.XML
=====================================

1. WHAT IS POM.XML

POM stands for Project Object Model.

pom.xml is the main configuration file of every Maven project.

It contains all information required to build and manage the project.

---

2. WHY DO WE NEED POM.XML

Without pom.xml developers need to

Download JAR files manually

Manage versions manually

Configure plugins manually

Build project manually

pom.xml keeps everything in one place.

---

3. INTERNAL WORKING

Developer adds Dependency

↓

Dependency stored in pom.xml

↓

Maven reads pom.xml

↓

Downloads required libraries

↓

Stores them in Local Repository

↓

Adds libraries to Project

↓

Application Ready

---

4. IMPORTANT TAGS

<groupId>

Unique identifier of the organization.

Example

com.devesh

---

<artifactId>

Project name.

Example

student-management-api

---

<version>

Current project version.

Example

1.0.0

---

<packaging>

Defines output type.

jar

war

---

<name>

Project Name

---

<description>

Project Description

---

5. DEPENDENCIES

Dependencies are external libraries used inside a project.

Example

Spring Web

Spring Data JPA

Spring Security

Validation

Lombok

MySQL Driver

Swagger

---

6. PARENT

Spring Boot projects generally inherit from

spring-boot-starter-parent

It provides

Default plugin versions

Dependency versions

Common configuration

Better compatibility

---

7. MAVEN REPOSITORY

Maven downloads libraries from

Maven Central Repository

Downloaded libraries are stored inside

Local Repository

(.m2 folder)

Future builds use local copy instead of downloading again.

---

8. DEPENDENCY SCOPES

compile

Available everywhere.

(Default)

---

runtime

Required while running application.

---

test

Only available during testing.

JUnit

Mockito

---

provided

Provided by external server.

Example

Tomcat

---

9. BUILD SECTION

The build section contains plugins.

Plugins help Maven perform tasks like

Compilation

Packaging

Testing

Spring Boot Packaging

---

10. ADVANTAGES

Centralized Configuration

Easy Dependency Management

Automatic Version Handling

Standard Project Structure

Supports Plugins

---

11. DISADVANTAGES

XML Syntax

Large pom.xml in big projects

Version conflicts if managed incorrectly

---

12. BACKEND USE CASES

REST APIs

Enterprise Applications

Microservices

Authentication Systems

Banking Applications

---

13. COMMON INTERVIEW QUESTIONS

Q. What is pom.xml?

Q. Why is pom.xml important?

Q. Difference between groupId and artifactId?

Q. What is spring-boot-starter-parent?

Q. Where are Maven dependencies stored?

Q. What are dependency scopes?

---

14. COMMON MISTAKES

Thinking pom.xml only stores dependencies.

Wrong.

It also stores

Plugins

Project Information

Build Configuration

Packaging

Repositories

---

15. MY UNDERSTANDING

pom.xml is the blueprint of a Maven project.

It tells Maven everything about the project including dependencies,
plugins, versions and build configuration, making project management
simple and organized.

=====================================
END OF TOPIC
=====================================
