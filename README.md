# Maven Memos for Building Microservices and Distributed Systems

These are the first steps to start Microservices and Distributed Systems from the ground with Maven.

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

![fraud-check-service_tree](https://user-images.githubusercontent.com/5893219/172763202-8e5b6670-6b09-4717-88e1-a0bc11dfd744.png)

## Open the project with the IDE (IntelliJ)

Set SDK if not set 

Delete SRC folder from the maven parent project (parent module)

## Open and set pom.xml correctly to start coding project

Main configuration is complete.

Parent project pom.xml file is set up properly.

## Open Maven

Reaload all Maven Projects

Wait for Sync to finish

Check for pluglins and dependencies

## Clean

Results:

"C:\Program Files\Java\jdk-18\bin\java.exe" -Dmaven.multiModuleProjectDirectory=D:\SpringBootProjects\fraud-check-service "-Dmaven.home=D:\TECH_ENV\ide\IntelliJ IDEA Community Edition 2022.1\plugins\maven\lib\maven3" "-Dclassworlds.conf=D:\TECH_ENV\ide\IntelliJ IDEA Community Edition 2022.1\plugins\maven\lib\maven3\bin\m2.conf" "-Dmaven.ext.class.path=D:\TECH_ENV\ide\IntelliJ IDEA Community Edition 2022.1\plugins\maven\lib\maven-event-listener.jar" "-javaagent:D:\TECH_ENV\ide\IntelliJ IDEA Community Edition 2022.1\lib\idea_rt.jar=62065:D:\TECH_ENV\ide\IntelliJ IDEA Community Edition 2022.1\bin" -Dfile.encoding=UTF-8 -classpath "D:\TECH_ENV\ide\IntelliJ IDEA Community Edition 2022.1\plugins\maven\lib\maven3\boot\plexus-classworlds-2.6.0.jar;D:\TECH_ENV\ide\IntelliJ IDEA Community Edition 2022.1\plugins\maven\lib\maven3\boot\plexus-classworlds.license" org.codehaus.classworlds.Launcher -Didea.version=2022.1 clean
[INFO] Scanning for projects...
[INFO] 
[INFO] -----------------< br.com.siomara:fraud-check-service >-----------------
[INFO] Building fraud-check-service 1.0-SNAPSHOT
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- maven-clean-plugin:2.5:clean (default-clean) @ fraud-check-service ---
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.495 s
[INFO] Finished at: 2022-06-11T03:35:52-03:00
[INFO] ------------------------------------------------------------------------

Process finished with exit code 0

## Validate

Results:

"C:\Program Files\Java\jdk-18\bin\java.exe" -Dmaven.multiModuleProjectDirectory=D:\SpringBootProjects\fraud-check-service "-Dmaven.home=D:\TECH_ENV\ide\IntelliJ IDEA Community Edition 2022.1\plugins\maven\lib\maven3" "-Dclassworlds.conf=D:\TECH_ENV\ide\IntelliJ IDEA Community Edition 2022.1\plugins\maven\lib\maven3\bin\m2.conf" "-Dmaven.ext.class.path=D:\TECH_ENV\ide\IntelliJ IDEA Community Edition 2022.1\plugins\maven\lib\maven-event-listener.jar" "-javaagent:D:\TECH_ENV\ide\IntelliJ IDEA Community Edition 2022.1\lib\idea_rt.jar=62068:D:\TECH_ENV\ide\IntelliJ IDEA Community Edition 2022.1\bin" -Dfile.encoding=UTF-8 -classpath "D:\TECH_ENV\ide\IntelliJ IDEA Community Edition 2022.1\plugins\maven\lib\maven3\boot\plexus-classworlds-2.6.0.jar;D:\TECH_ENV\ide\IntelliJ IDEA Community Edition 2022.1\plugins\maven\lib\maven3\boot\plexus-classworlds.license" org.codehaus.classworlds.Launcher -Didea.version=2022.1 validate
[INFO] Scanning for projects...
[INFO] 
[INFO] -----------------< br.com.siomara:fraud-check-service >-----------------
[INFO] Building fraud-check-service 1.0-SNAPSHOT
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.343 s
[INFO] Finished at: 2022-06-11T03:36:33-03:00
[INFO] ------------------------------------------------------------------------

Process finished with exit code 0

## Final notes

Set up is complete

See **"fraud-check-service"** from now on.
