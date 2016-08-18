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
