# How to install Java

There are a variety of ways to install Java.  It's pretty easy if you use a package manager.

Spark requires Java 8 or 17.  You need to make sure you install the right Java version when using Spark.

## Install Java on Macbook

You can install Java on a Macbook with package managers (SDKMAN, jenv, coursier) or manually.  You only need to use one option of course.

**Install Java with SDKMAN**

You can install SDKMAN by running the following command: `curl -s "https://get.sdkman.io" | bash`

Close your Terminal and reopen it.

Then you can install Java 8 with this command: `sdk install java 8.0.272.hs-adpt`.

Set this as your default Java version: `sdk default java
8.0.272.hs-adpt`.

Run this command to ensure that Java has been installed successfully: `java -version`.

**Install Java with jenv**

You can install jenv by running the following command: `brew install jenv`.

Close your Terminal and reopen it.

Then you can install Java 8 with this command: `brew cask install adoptopenjdk/openjdk/adoptopenjdk8`.

Add Java 8 to jenv: `jenv add /Library/Java/JavaVirtualMachines/adoptopenjdk-8.jdk/Contents/Home/`.

Set this as your default Java version: `jenv global openjdk64-1.8.0.265`.

Run this command to ensure that Java has been installed successfully: `java -version`.

**Install Java with coursier**

TODO

## Install Java on Windows

TODO

## Install Java on Linux

TODO

