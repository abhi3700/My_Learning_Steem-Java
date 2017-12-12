## Introduction

## SteemJ dependency

## Slf4j dependency
As mentioned in the ["Steem-Java wiki"](https://github.com/marvin-we/steem-java-api-wrapper/wiki/Logging#introduction):
> Prior to SteemJ version 0.4.0, SteemJ was shipped with a logging framework implementation. As this is a bad practice for several reasons, SteemJ 0.4.0 removed this implementation and allows you to configure the logging on your own.

> To achieve this, SteemJ only contains the slf4j-api and expects you, to add the slf4j implementation of your choice to your project. 

NOTE: The possible error codes while compiling codes can be found [here](https://www.slf4j.org/codes.html) with the solution.
## Log4j dependency
Ref. - https://logging.apache.org/log4j/2.0/maven-artifacts.html

## Coding an Steem-based App 
Here, we will be developing an **Android** App whose backend will be hosted on **Steem-blockchain**. Although this is a simple App which will fetch the data (i.e. reading, not writing). In subsequent tutorials, we will be learning _reading from_ and _writing to_ the Steem-database in lot more details.

