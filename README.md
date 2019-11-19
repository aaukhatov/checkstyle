# checkstyle

## Intro

Правила описываются с помощью плагина Checkstyle [http://checkstyle.sf.net/](http://checkstyle.sf.net/).

Для соблюдения всеми разработчиками **Coding Style**, необходимо **включить проверку на стадию Continuous Integration** с помощью плагинов:

- [Apache Maven Checkstyle Plugin](https://maven.apache.org/plugins/maven-checkstyle-plugin/)
- [Gradle Checkstyle Plugin](https://docs.gradle.org/current/userguide/checkstyle_plugin.html)

## Project Structure

Структура проекта должна соответствовать [Standard Directory Layout](https://maven.apache.org/guides/introduction/introduction-to-the-standard-directory-layout.html).

### Apache Maven
```text
project-name
├── pom.xml
├── .gitignore
├── LICENSE
├── CHANGELOG.md
├── README.md
└── src
    ├── docker
    │   └── Dockerfile
    ├── itest
    │   ├── java
    │   ├── kotlin
    │   └── resources
    ├── main
    │   ├── java
    │   ├── kotlin
    │   └── resources
    └── test
        ├── java
        ├── kotlin
        └── resources
```

### Gradle
```text
project-name
├── build.gradle
├── gradle.properties
├── setting.gradle
├── .gitignore
├── LICENSE
├── CHANGELOG.md
├── README.md
└── src
    ├── docker
    │   └── Dockerfile
    ├── itest
    │   ├── java
    │   ├── kotlin
    │   └── resources
    ├── main
    │   ├── java
    │   ├── kotlin
    │   └── resources
    └── test
        ├── java
        ├── kotlin
        └── resources
```

## Source File

### Encoding
Файлы с исходным кодом должны быть в кодировке `UTF-8`.