# springcode

<!-- TOC -->

- [springcode](#springcode)
- [Things to learn and research](#things-to-learn-and-research)
- [Plan](#plan)
- [Project Structure](#project-structure)
- [Install](#install)
    - [Java](#java)

<!-- /TOC -->

---
# Things to learn and research

In no particular order, my plan is to use the following resources to learn and research. The artifacts for each learning resource will be kept under a separate folder, e.g. doc/Bunker2019, img/Bunker2019, etc.

* [Spring Framework: Creating Your First Spring Boot Application](https://app.pluralsight.com/library/courses/creating-first-spring-boot-application) | Pluralsight Bunker2019

---
# Plan
- [ ] [Complete Spring Framework: Creating Your First Spring Boot Application](./doc/Bunker2019/README.md#complete-spring-framework-creating-your-first-spring-boot-application)
---
# Project Structure

```
springcode
|- README.md
+- doc
   +- Bunker2019
      |- README.md
+- img
   +- Bunker2019
      |- build.png
      |- dbschema.png
+- src
   +- Bunker2019
      +- conference-demo
         |- HELP.md
         |- mvnw
         |- mvnw.cmd
         |- pom.xml
         +- .mvn
         +- src
            +- main
               +- java
                  +- com
                     +- pluralsight
                        +- conferencedemo
                           |- ConferenceDemoApplication.java
               +- resources
            +- test
               +- java
                  +- com
                     +- pluralsight
                        +- conferencedemo
                           |- ConferenceDemoApplicationTests.java
      +- ps-first-spring-boot-app
         |- README.md
         +- database
            +- mysql
            +- postgresql
```

---
# Install

## Java

The **AdoptOpenJDK** tap has been officially deprecated in favor of **temurin**, and will receive no further updates after 1/8/2021.

If you are on a Mac and using **Homebrew**, all you need to do to install the Java JDK is:

```sh
brew tap homebrew/cask-versions
brew install --cask temurin8
```

> Note: `temurin8` installs Java JDK 8.

Verify that Java JDK has been installed:

```sh
java -version
openjdk version "1.8.0_312"
OpenJDK Runtime Environment (Temurin)(build 1.8.0_312-b07)
OpenJDK 64-Bit Server VM (Temurin)(build 25.312-b07, mixed mode)
```