# eclipse-gradle-problem
An example of broken project in eclipse.

Steps to reproduce:

1. in Eclipse `File/Import/Gradle Project`
2. import root project, nested module will be imported automatically

Expected behavior: Class ATest is compilable.

Actual behavior: Class ATest is not compilable (`com.google.common.collect.ImmutableMap` not found).

Everything works fine if you run from CLI however:

```
$ gradle wrapper
$ ./gradlew build accTest
```
Eclipse version: Neon Release (4.6.0)

Buildship version: 1.0.18.v20160817-1550

Gradle version: 3.0

Here is relevant output of `$ ./gradlew dependencies`
```
:dependencies

------------------------------------------------------------
Root project
------------------------------------------------------------

accTestCompile - Dependencies for source set 'acc test'.
+--- com.google.guava:guava:19.0
\--- org.slf4j:slf4j-api:1.7.21

accTestCompileClasspath - Compile classpath for source set 'acc test'.
+--- com.google.guava:guava:19.0
\--- org.slf4j:slf4j-api:1.7.21

accTestCompileOnly - Compile dependencies for source set 'acc test'.
+--- com.google.guava:guava:19.0
\--- org.slf4j:slf4j-api:1.7.21

accTestRuntime - Runtime dependencies for source set 'acc test'.
+--- com.google.guava:guava:19.0
\--- org.slf4j:slf4j-api:1.7.21
...
```
