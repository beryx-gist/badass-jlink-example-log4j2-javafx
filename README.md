[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/beryx-gist/badass-jlink-example-log4j2-javafx/blob/master/LICENSE)
[![Build Status](https://img.shields.io/travis/beryx-gist/badass-jlink-example-log4j2-javafx/master.svg?label=Build)](https://travis-ci.org/beryx-gist/badass-jlink-example-log4j2-javafx)

## Badass JLink Plugin Example: log4j2 and JavaFX ##

A small JavaFX application using log4j2 that shows how to use the [Badass JLink Plugin](https://github.com/beryx/badass-jlink-plugin/).

The plugin is configured in `build.gradle` as follows:

```
plugins {
    id 'application'
    id 'org.openjfx.javafxplugin' version '0.0.5'
    id 'org.beryx.jlink' version '2.1.9'
}

repositories {
    mavenCentral()
}

dependencies {
    compile 'org.apache.logging.log4j:log4j-core:2.11.1'
}

javafx {
    modules = ['javafx.controls']
}

mainClassName = "hellofx/org.openjfx.HelloFX"

jlink {
    options = ['--strip-debug', '--compress', '2', '--no-header-files', '--no-man-pages']
    launcher {
        name = 'helloFX'
    }
    forceMerge('log4j-api')
}
```

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
