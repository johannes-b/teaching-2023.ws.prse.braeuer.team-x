# Simple Calculator

## Build App

First, istall Maven according to: https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html

```
mvn -v

Apache Maven 3.9.6 (bc0240f3c744dd6b6ec2920b3cd08dcc295161ae)
Maven home: C:\Program Files\CLI\apache-maven
Java version: 21.0.2, vendor: Oracle Corporation, runtime: C:\Program Files\Java\jdk-21
Default locale: en_US, platform encoding: UTF-8
OS name: "windows 11", version: "10.0", arch: "amd64", family: "windows"
```

```
java version

java version "21.0.2" 2024-01-16 LTS
Java(TM) SE Runtime Environment (build 21.0.2+13-LTS-58)
Java HotSpot(TM) 64-Bit Server VM (build 21.0.2+13-LTS-58, mixed mode, sharing)
```

To build app, execute the maven goal `package`:
```
mvn package
```

To run the app, run the command:
```
java -jar .\target\calculator-0.0.1.jar
```