## Introduction

## SteemJ dependency
The dependency is mentioned in the ["Steem-Java wiki"](https://github.com/marvin-we/steem-java-api-wrapper/wiki/How-to-add-SteemJ-to-your-project) page. Here, all the installations for different **"build management tools"** are available here - 
* Maven
* Ivy
* **Gradle** (discussed in this tutorial)
* Scala
* Groovy
* Download

## Slf4j dependency
As mentioned in the ["Steem-Java wiki"](https://github.com/marvin-we/steem-java-api-wrapper/wiki/Logging#introduction):
> Prior to SteemJ version 0.4.0, SteemJ was shipped with a logging framework implementation. As this is a bad practice for several reasons, SteemJ 0.4.0 removed this implementation and allows you to configure the logging on your own. 

> To achieve this, SteemJ only contains the _slf4j-api_ and expects you, to add the _slf4j_ implementation of your choice to your project.

So, we have to add the other _slf4j_ implementations into our project. Follow the guide [here](https://github.com/marvin-we/steem-java-api-wrapper/wiki/Logging#example-configuration)
> One good example of an alternative slf4j implementation is log4j-slf4j-impl, which implements the slf4j-api and adds the powerfull configuration options of log4j2.

In the build management tools, follow this -
* Maven
```
<!-- https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-slf4j-impl -->
<dependency>
    <groupId>org.apache.logging.log4j</groupId>
    <artifactId>log4j-slf4j-impl</artifactId>
    <version>2.1</version>
</dependency>

```


NOTE: The possible error codes while compiling codes can be found [here](https://www.slf4j.org/codes.html) along with the solution.
## Log4j dependency
Ref. - https://logging.apache.org/log4j/2.0/maven-artifacts.html

## Coding an Steem-based App 
Here, we will be developing an **Android** App whose backend will be hosted on **Steem-blockchain**. Although this is a simple App which will fetch the data (i.e. reading, not writing). In subsequent tutorials, we will be learning _reading from_ and _writing to_ the Steem-database in lot more details.

