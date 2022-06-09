# Maven Memos

## Download Apache Maven X.X.X

https://maven.apache.org/download.cgi

## Installation

1. Maven is a Java tool, so assure a JDK is installed.
2. Either set the JAVA_HOME environment variable pointing to the JDK installation or have the java executable on the PATH.
3. Unzip Maven to a folder (ex: apache-maven-3.8.5).
4. Add the bin directory of the created directory apache-maven-3.8.5 to the PATH environment variable.
5. Confirm installation running "mvn -v" or "mvm --version" in a new shell/DOS.

Results:

      mvn --version

      Apache Maven 3.8.5 (3599d3414f046de2324203b78ddcf9b5e4388aa0)
      Maven home: D:\TECH_ENV\maven\apache-maven-3.8.5
      Java version: 18-ea, vendor: Oracle Corporation, runtime: D:\TECH_ENV\java\jdk-18
      Default locale: pt_BR, platform encoding: Cp1252
      OS name: "windows 10", version: "10.0", arch: "amd64", family: "windows"

## Check environment variable on Windows

echo %JAVA_HOME%

C:\Program Files\Java\jdkX.X.X

## Creating the project

1. Create a directory for the project and start a shell in that directory.
2. On the command line, execute the following Maven command:

      mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false
      
**OBSERVATION 1:** There is no need to create a folder for the project because the command above will create it. So just cd to the place where you want the project folder to be created. In case the project folder exists, the command will not cause an error. It will cause just a warning saying that the folder already exixts. Notice that the group Id below is just the domain, the ".app" was not appended.

**OBSERVATION 2:** If you have just installed Maven, it may take a while on the first run. This is because Maven is downloading the most recent artifacts (plugin jars and other files) into your local repository. You may also need to execute the command a couple of times before it succeeds. This is because the remote server may time out before your downloads are complete. Don't worry, there are ways to fix that.

      mvn archetype:generate -DgroupId=br.com.siomara -DartifactId=fraud-check-service -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false
      
![fraud-check-service](https://user-images.githubusercontent.com/5893219/172744242-02605300-d87c-4ef2-af14-0c10f3ec78a5.png)

            D:\SpringBootProjects>cd fraud-check-service

            D:\SpringBootProjects\fraud-check-service>tree /f /a

![fraud-check-service_tree](https://user-images.githubusercontent.com/5893219/172756119-e3916cc9-1c84-4782-802e-b39059c358b9.png)

