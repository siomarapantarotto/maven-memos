# Maven Memos

## Download Apache Maven X.X.X

https://maven.apache.org/download.cgi

## Installation

1. Assure a JDK is installed.
2. Either set the JAVA_HOME environment variable pointing to the JDK installation or have the java executable on the PATH.
3. Unzip Maven to a folder (ex: apache-maven-3.8.5).
4. Add the bin directory of the created directory apache-maven-3.8.5 to the PATH environment variable.
5. Confirm installation running "mvn -v" or "mvm --version" in a new shell/DOS.

Results:

...>mvn --version
Apache Maven 3.8.5 (3599d3414f046de2324203b78ddcf9b5e4388aa0)
Maven home: D:\TECH_ENV\maven\apache-maven-3.8.5
Java version: 18-ea, vendor: Oracle Corporation, runtime: D:\TECH_ENV\java\jdk-18
Default locale: pt_BR, platform encoding: Cp1252
OS name: "windows 10", version: "10.0", arch: "amd64", family: "windows"

## Check environment variable on Windows

echo %JAVA_HOME%

C:\Program Files\Java\jdkX.X.X

