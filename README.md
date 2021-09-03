[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/beryx-gist/badass-jlink-example-log4j2-javafx/blob/master/LICENSE)
[![Build Status](https://github.com/beryx-gist/badass-jlink-example-log4j2-javafx/workflows/Gradle%20Build/badge.svg)](https://github.com/beryx-gist/badass-jlink-example-log4j2-javafx/actions?query=workflow%3A%22Gradle+Build%22)

## Badass JLink Plugin Example: log4j2 and JavaFX ##

A small JavaFX application using log4j2 that shows how to use the [Badass JLink Plugin](https://github.com/beryx/badass-jlink-plugin/).


### Usage
**Running with gradle:**
```
./gradlew run
```

A window containing the text `HelloFX` should appear on the screen and the following text should be printed on the console:
```
[JavaFX Application Thread] INFO  org.openjfx.HelloFX - hellofx!
```


**Creating and executing a custom runtime image:**
```
./gradlew jlink
cd build/image/bin
./helloFX
```

A window containing the text `HelloFX` should appear on the screen and the following text should be printed on the console:
```
[JavaFX Application Thread] INFO  org.openjfx.HelloFX - hellofx!
```


**Creating installable packages**
```
./gradlew jpackage
```

The above command will generate the platform-specific installers in the `build/jpackage` directory.

:bulb: You can check the artifacts produced by the [GitHub actions used to build this project](https://github.com/beryx-gist/badass-jlink-example-log4j2-javafx/actions?query=workflow%3A%22Gradle+Build%22) and download an application package for your platform (such as [from here](https://github.com/beryx-gist/badass-jlink-example-log4j2-javafx/actions/runs/1198565779#artifacts)).
