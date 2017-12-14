![](https://steemit-production-imageproxy-thumbnail.s3.amazonaws.com/U5dsRkzYuy1zS2U1nq4GF5L5nyNv231_1680x8400)
## Introduction
For coding the Steem blockchain for _read from_ and _write to_ operations, we need a library. The library called - [**SteemJ**](https://github.com/marvin-we/steem-java-api-wrapper) is to be used in the whole tutorial series. 

Actually, while coding the **SteemJ**, we have to find out where exactly the exception is occuring and at which line of code, the error is present. In order to meet the need, there is an initiative taken by the Apache foundation providing us with _"SL4J"_ and _"Log4J"_. These are for logging the data for fetching the steem-blockchain.
But, later we will switch to a different logger called [**Logger**](https://github.com/orhanobut/logger). This is way better than using the _slf4j_ & _log4j_.
Although, there are multiple build management systems. But here we are concerned with _Gradle_ which is used in building Android apps.

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
* Leiningen
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
* **Gradle** (discussed in this tutorial)
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
* Leiningen
```
;; https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-slf4j-impl
[org.apache.logging.log4j/log4j-slf4j-impl "2.1"]
```
* Download:- 
 Please, download this file- "log4j-slf4j-impl-2.10.0.jar" according to the required version from this [page](http://central.maven.org/maven2/org/apache/logging/log4j/log4j-slf4j-impl/2.10.0/) 


NOTE: The possible error codes while compiling codes can be found [here](https://www.slf4j.org/codes.html) along with the solution.
## Log4j dependency
Log4j means "logging for java". It is very important for building distributed applications (normally blockchain-based apps). This is because there is no debugger available for this libraries like in case of "steem-core". So, we need to feed this additional codes in order to note "what is happening?" in every lines of program during execution.
A brief history - log4j was closed in 2015. Read the [post](https://blogs.apache.org/foundation/entry/apache_logging_services_project_announces). But resumed now.
Read about [log4j 2](http://logging.apache.org/log4j/2.x/index.html)

Log4j 2 is divided into 2 parts
**log4j-api** -> the API that provides the interface that applications should code to.
**log4j-core** -> an implementation required during runtime, not at compile time.

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
* **Gradle** (discussed in this tutorial)
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
* Leiningen
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
 
#### Practical example: 
Coding a logging example for better understanding.
For the methods - **debug, info, error, warn, fatal** to appear, we have to add a configuration file - ```log4j2.xml```
```
<?xml version="1.0" encoding="UTF-8"?>
<Configuration status="info">
	<Appenders>
		<Console name="Console" target="SYSTEM_OUT">
			<PatternLayout pattern="%d{HH:mm:ss.SSS} [%t] %-5level %logger{36} - %msg%n" />
		</Console>
	</Appenders>
	<Loggers>
		<Root level="debug">
			<AppenderRef ref="Console" />
		</Root>
	</Loggers>
</Configuration>
```

**JAVA implementation**
```java
public class LoggerMethods {

	 // get a logger instance
	public static Logger logger = Logger.getLogger(LoggerMethods.class);
  
  	public static void main(String[] args) {
		LoggerExample example = new LoggerExample();
		example.testLoggerDebug();  // Debug method
		example.testLoggerInfo();   // Info method
    		example.testLoggerError();  // Error method
		example.testLoggerWarn();   // Warn method
		example.testLoggerFatal();  // Fatal method
	}

	public void testLoggerDebug() {
		logger.debug("Hello.. im in Debug method");
	}

	public void testLoggerInfo() {
		logger.info("Hello.. im in Info method");
	}
  
  	public void testLoggerError() {
		logger.error("Hello.. im in Error method");
	}

	public void testLoggerWarn() {
		logger.warn("Hello.. im in Warn method");
	}

	public void testLoggerFatal() {
		logger.fatal("Hello.. im in Fatal method");
	}
}
```
## Logger Android
![](https://github.com/abhi3700/My_Learning_Steem-Java/blob/master/Images/Logger.png)

* **Gradle** (discussed in this tutorial)
```
// Logger android
compile 'com.orhanobut:logger:2.1.1'
```
Below are the basic codes which are to be added wherever needed. By default, the TAG is _PRETTY_LOGGER_.
```
Logger.addLogAdapter(new AndroidLogAdapter());  // intialising the Logger
Logger.d("debug")
Logger.i("info")
Logger.e("error")
Logger.w("warn")
Logger.v("verbose")
```


## Coding a Steem-based App 
Here, we will be developing an **Android** App whose backend will be hosted on **Steem-blockchain**. Although this is a simple App which will fetch the data (i.e. reading, not writing). In subsequent tutorials, we will be learning _reading from_ and _writing to_ the Steem-database in lot more details.

So, the simple front-end in xml:- 
```
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="in.topux.steemit2.HomeActivity">


    <TextView
        android:id="@+id/username_value"
        android:layout_width="65dp"
        android:layout_height="21dp"
        android:layout_marginLeft="8dp"
        android:layout_marginStart="8dp"
        android:text="TextView"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/price_value"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginLeft="8dp"
        android:layout_marginTop="108dp"
        android:text="TextView2"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/username_value" />
</android.support.constraint.ConstraintLayout>
```

The code in java :-
```
public class HomeActivity extends AppCompatActivity {

    private TextView usernameValue;
    private TextView priceValue;

    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.home_activity);

        Logger.addLogAdapter(new AndroidLogAdapter());

        usernameValue = (TextView) findViewById(R.id.username_value);
        priceValue = (TextView) findViewById(R.id.price_value);

	// Steem blockchain connection using AsyncTask
        new SteemAsyncTask().execute();
    }

    private static class MyCustomCallback extends BlockAppliedCallback {
        @Override
        public void onNewBlock(SignedBlockHeader signedBlockHeader) {
            Logger.i("Signed block addition",signedBlockHeader.toString());
        }
    }

    private class SteemAsyncTask extends AsyncTask<Void,Void,String[]>{

        @Override
        protected String[] doInBackground(Void... voids) {
            String[] strings = new String[100]; // 100 is a random number (chosen) of strings inside the array.
            try{
                // adding a new API wrapper
                SteemJ steemJ = new SteemJ();
                Logger.i("Steem blockchain connected");

                steemJ.setBlockAppliedCallback(new MyCustomCallback());

                strings[0] = steemJ.getHardforkVersion();
                Logger.i("HF version fetched");

                MarketTicker marketTicker = steemJ.getTicker();
                strings[1] = marketTicker.toString();
                Logger.i("get market ticker");

            } catch (SteemCommunicationException e){
                Logger.e("SteemCommunicationException " + e.getMessage());
            } catch (SteemResponseException e){
                Logger.e("SteemResponseException " + e.getMessage());
            } catch (NetworkOnMainThreadException e){
                Logger.e("NetworkOnMainThreadException " + e.getMessage());
            }
            return strings;
        }

        @Override
        protected void onPostExecute(String[] strings) {
            super.onPostExecute(strings);
            usernameValue.setText(strings[0]);
            priceValue.setText(strings[1]);
        }
    }
}
```

This is a simple example which shows fetching the data- _hardfork version_ and _market ticker_. Like this, we can fetch many more such data.

That's all for now.

View in [steemit](https://steemit.com/utopian-io/@abhi3700/learn-steem-java-with-android-1-installation-guide)
