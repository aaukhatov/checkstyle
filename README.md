# checkstyle

## Intro

The following list offers practical advices that will help you write better Java code.

These rules has been written on Checkstyle [http://checkstyle.sf.net/](http://checkstyle.sf.net/).

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

### Выравнивание
* Использовать пробелы (не табы), один отступ - 4 пробела
* Строки должны заканчиваться на **LF** (Unix way), не CRLF (Windows way)
* Длина строки не должна превышать 120 символов (исключение import statements)
* Файл должен заканчиваться пустой строкой

## Структура файла с исходным кодом
1. Лицензия
2. Пакет (package statement)
3. Пустая строка
4. Импорт зависимостей (import statements)
5. Пустая строка
6. Один класс верхнего уровня

### Лицензия
В каждый файл с исходным кодом следует помещать лицензию в заголовок.

#### Полный текст с лицензией

```java
 /*
 * Copyright (C) 2019 Arthur Aukhatov
 *
 * Licensed under the Apache License, Version 2.0 (the "License");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 *      https://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */
 ```

#### Сокращенный текст с лицензией

 ```java
/*
 * Copyright (C) 2019 Arthur Aukhatov
 *
 * This software may be modified and distributed under the terms
 * of the MIT license. See the LICENSE file for details.
 */
 ```

### Import Statements

Зависимости в **import statements** следует структурировать следующим образом:

 * import `java.*`
 * `<blank line>`
 * import `javax.*`
 * `<blank line>`
 * 3rd party imports
 * `<blank line>`
 * import `your.own.imports`
 * `<blank line>`
 * other static imports

> Импорты с `wildcard` не рекомендуется использовать - если импортов так много, значит следует разбить класс на несколько

### Java Class Structure

Описание порядка организации/структуризации элементов `java` класса:

1. **static** поля класса
2. **public** поля экземпляра
3. **protected** поля экземпляра
4. **private** поля экземпляра
5. **конструктор без параметров**
6. **другие конструкторы**
7. **private** методы, который вызываются из конструктора
8. **static** фабричные методы
9. **getters**, **setters**
10. реализации методов интерфейса
11. **private** или **protected** методы вызываемые из метода реализации интерфейса
12. другие методы
13. `equals`, `hashCode`, `toString`
