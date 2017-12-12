## Introduction

## SteemJ dependency
The dependency is mentioned in the ["Steem-Java wiki"](https://github.com/marvin-we/steem-java-api-wrapper/wiki/How-to-add-SteemJ-to-your-project) page. Here, all the installations for different **"build management tools"** are available [here](https://mvnrepository.com/artifact/eu.bittrade.libs/steemj-core/0.4.3) i.e. latest version - 0.4.3 : 
* Maven
```
[...]
<dependency>
  <groupId>eu.bittrade.libs</groupId>
  <artifactId>steemj-core</artifactId>
  <version>0.4.3</version>
</dependency>
[...]
```
* Ivy
```
[...]
<dependency org="eu.bittrade.libs" name="steemj-core" rev="0.4.3" />
[...]
```
* **Gradle** (discussed in this tutorial)
```
// 'compile' is deprecated now in "Android Studio 3.0.1". Instead use 'api'
[...]
api 'eu.bittrade.libs:steemj-core:0.4.3'
[...]
```
* Scala
```
[...]
libraryDependencies += "eu.bittrade.libs" % "steemj-core" % "0.4.3"
[...]
```
* Groovy
```
[...]
@Grab(group='eu.bittrade.libs', module='steemj-core', version='0.4.3')
[...]
```
* Leinigen
```
[...]
[eu.bittrade.libs/steemj-core "0.4.3"]
[...]
```
* Download:- 
Please, download from [here](https://mvnrepository.com/artifact/eu.bittrade.libs/steemj-core) as per required according to the version.

## Slf4j dependency
As mentioned in the ["Steem-Java wiki"](https://github.com/marvin-we/steem-java-api-wrapper/wiki/Logging#introduction):
> Prior to SteemJ version 0.4.0, SteemJ was shipped with a logging framework implementation. As this is a bad practice for several reasons, SteemJ 0.4.0 removed this implementation and allows you to configure the logging on your own. 

> To achieve this, SteemJ only contains the _slf4j-api_ and expects you, to add the _slf4j_ implementation of your choice to your project.

So, we have to add the other _slf4j_ implementations into our project. Follow the guide [here](https://github.com/marvin-we/steem-java-api-wrapper/wiki/Logging#example-configuration)
> One good example of an alternative slf4j implementation is log4j-slf4j-impl, which implements the slf4j-api and adds the powerfull configuration options of log4j2.

In the build management tools, follow below for implementing the [_log4j-slf4j-impl_](https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-slf4j-impl/2.10.0) i.e. latest version- 2.10.0  :
* Maven
```
<!-- https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-slf4j-impl -->
<dependency>
    <groupId>org.apache.logging.log4j</groupId>
    <artifactId>log4j-slf4j-impl</artifactId>
    <version>2.1</version>
</dependency>
```
* Ivy
```
<!-- https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-slf4j-impl -->
<dependency org="org.apache.logging.log4j" name="log4j-slf4j-impl" rev="2.1"/>
```
* Gradle
```
// 'compile' is deprecated now in "Android Studio 3.0.1". Instead use 'api'
api 'org.apache.logging.log4j:log4j-slf4j-impl:2.1'  
```
* Scala
```
// https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-slf4j-impl
libraryDependencies += "org.apache.logging.log4j" % "log4j-slf4j-impl" % "2.1"
```
* Groovy
```
// https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-slf4j-impl
@Grapes(
    @Grab(group='org.apache.logging.log4j', module='log4j-slf4j-impl', version='2.1')
)
```
* Leinigen
```
;; https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-slf4j-impl
[org.apache.logging.log4j/log4j-slf4j-impl "2.1"]
```
* Download:- 
 Please, download this file- "log4j-slf4j-impl-2.10.0.jar" according to the required version from this [page](http://central.maven.org/maven2/org/apache/logging/log4j/log4j-slf4j-impl/2.10.0/) 


NOTE: The possible error codes while compiling codes can be found [here](https://www.slf4j.org/codes.html) along with the solution.
## Log4j dependency

**log4j-api** ->
**log4j-core** ->

To know more, click [here](http://logging.apache.org/log4j/1.2/)

In the build management tools, follow below for implementing the [log4j-api](https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-api/2.10.0) and [log4j-core](https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-core/2.10.0) i.e. latest versions- 2.10.0 :
* Maven
```
// log4j-api
<!-- https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-api -->
<dependency>
    <groupId>org.apache.logging.log4j</groupId>
    <artifactId>log4j-api</artifactId>
    <version>2.10.0</version>
</dependency>

// log4j-core
<!-- https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-core -->
<dependency>
    <groupId>org.apache.logging.log4j</groupId>
    <artifactId>log4j-core</artifactId>
    <version>2.10.0</version>
</dependency>
```
* Ivy
```
// log4j-api
<!-- https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-api -->
<dependency org="org.apache.logging.log4j" name="log4j-api" rev="2.10.0"/>

// log4j-core
<!-- https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-core -->
<dependency org="org.apache.logging.log4j" name="log4j-core" rev="2.10.0"/>
```
* Gradle
```
// log4j-api
// https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-api
// 'compile' is deprecated now in "Android Studio 3.0.1". Instead use 'api'
api 'org.apache.logging.log4j:log4j-api:2.10.0'

// log4j-core
api 'org.apache.logging.log4j:log4j-core:2.10.0'
```
* Scala
```
// log4j-api
// https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-api
libraryDependencies += "org.apache.logging.log4j" % "log4j-api" % "2.10.0"

// log4j-core
// https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-core
libraryDependencies += "org.apache.logging.log4j" % "log4j-core" % "2.10.0"
```
* Groovy
```
// log4j-api
// https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-api
@Grapes(
    @Grab(group='org.apache.logging.log4j', module='log4j-api', version='2.10.0')
)

// log4j-core
// https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-core
@Grapes(
    @Grab(group='org.apache.logging.log4j', module='log4j-core', version='2.10.0')
)
```
* Leinigen
```
// log4j-api
;; https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-api
[org.apache.logging.log4j/log4j-api "2.10.0"]

// log4j-core
;; https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-core
[org.apache.logging.log4j/log4j-core "2.10.0"]
```
* Download:- 
 Please, download this file- "log4j-api-2.10.0.jar" according to the required version from this [page](http://central.maven.org/maven2/org/apache/logging/log4j/log4j-api/2.10.0/) and file - "log4j-core-2.10.0.jar" according to the required version from this [page](http://central.maven.org/maven2/org/apache/logging/log4j/log4j-core/2.10.0/)
 
Ref. - https://logging.apache.org/log4j/2.0/maven-artifacts.html

## Coding an Steem-based App 
Here, we will be developing an **Android** App whose backend will be hosted on **Steem-blockchain**. Although this is a simple App which will fetch the data (i.e. reading, not writing). In subsequent tutorials, we will be learning _reading from_ and _writing to_ the Steem-database in lot more details.

