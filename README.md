# kt-hello-world

Create a Java Application using gradle.

```sh
gradle init
Starting a Gradle Daemon (subsequent builds will be faster)

Select type of project to generate:
  1: basic
  2: application
  3: library
  4: Gradle plugin
Enter selection (default: basic) [1..4] 2

Select implementation language:
  1: C++
  2: Groovy
  3: Java
  4: Kotlin
  5: Scala
  6: Swift
Enter selection (default: Java) [1..6] 4

Split functionality across multiple subprojects?:
  1: no - only one application project
  2: yes - application and library projects
Enter selection (default: no - only one application project) [1..2] 1

Select build script DSL:
  1: Groovy
  2: Kotlin
Enter selection (default: Kotlin) [1..2] 1

Project name (default: kt-hello-world): 
Source package (default: kt.hello.world): 

> Task :init
Get more help with your project: https://docs.gradle.org/7.1.1/samples/sample_building_kotlin_applications.html

BUILD SUCCESSFUL in 24s
2 actionable tasks: 2 executed
```

## Runnable Jar

Add jar task on _app/build.gradle_ file:

```
jar {
    archiveBaseName = 'kt-hello-world'
    archiveVersion = '0.0.1' 
    manifest {
        attributes 'Main-Class': 'kt.hello.world.AppKt'
    }
}
```

> You need to add sufix __Kt__ in the class name when using Kotlin

Create the jar file:

```sh
gradle jar

BUILD SUCCESSFUL in 842ms
3 actionable tasks: 1 executed, 2 up-to-date
```

Execute it:

```sh
java -jar ./app/build/libs/kt-hello-world-0.0.1.jar
Hello World!
```
