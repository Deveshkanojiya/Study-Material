=====================================
MAVEN
=====================================

1. WHAT IS MAVEN

Maven is a Build Automation and Dependency Management Tool for Java projects.

It helps developers build, manage and package Java applications efficiently.

Maven automatically downloads required libraries and manages the project lifecycle.

---

2. WHY DO WE NEED MAVEN

Without Maven, developers need to:

Download JAR files manually

Add libraries manually

Handle library versions manually

Compile project manually

Package project manually

This process becomes difficult as the project grows.

Maven automates all these tasks.

---

3. INTERNAL WORKING

Developer adds Dependency

↓

Dependency added in pom.xml

↓

Maven checks Local Repository

↓

If not found

↓

Downloads from Maven Central Repository

↓

Stores in Local Repository

↓

Adds dependency to Project

↓

Application Ready

---

4. IMPORTANT FEATURES

Dependency Management

Build Automation

Project Standardization

Plugin Support

Lifecycle Management

Repository Management

---

5. MAVEN LIFECYCLE

validate

↓

compile

↓

test

↓

package

↓

verify

↓

install

↓

deploy

---

6. COMMON MAVEN COMMANDS

mvn clean

Deletes previous build files.

---

mvn compile

Compiles Java source code.

---

mvn test

Runs test cases.

---

mvn package

Creates executable JAR or WAR file.

---

mvn install

Installs project into Local Repository.

---

mvn clean install

Deletes old build, compiles, tests and installs the project.

---

7. ADVANTAGES

Automatic Dependency Management

Easy Build Process

Version Management

Standard Project Structure

Large Plugin Ecosystem

Reduces Manual Work

---

8. DISADVANTAGES

Learning Curve

XML Configuration

Internet required for first dependency download

Large projects may take time to build

---

9. BACKEND USE CASES

Spring Boot Projects

REST APIs

Microservices

Enterprise Applications

CI/CD Pipelines

Large Team Projects

---

10. COMMON INTERVIEW QUESTIONS

Q. What is Maven?

Q. Why do we use Maven?

Q. Difference between Maven and Gradle?

Q. What is Maven Repository?

Q. What is mvn clean install?

Q. What is the Maven Lifecycle?

---

11. COMMON MISTAKES

Thinking Maven is only used for downloading dependencies.

Wrong.

Maven also manages:

Project Build

Testing

Packaging

Plugins

Deployment

---

12. MY UNDERSTANDING

Maven is the build tool of a Java project.

Instead of manually managing libraries and build steps, Maven automates dependency management, compilation, testing and packaging, making development faster and more organized.

=====================================
END OF TOPIC
=====================================
