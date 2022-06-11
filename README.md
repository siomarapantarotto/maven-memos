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

![fraud-check-service_tree](https://user-images.githubusercontent.com/5893219/172763202-8e5b6670-6b09-4717-88e1-a0bc11dfd744.png)

## Open the project with the IDE (IntelliJ)

Set SDK if not set 

Delete SRC folder from the maven parent project (parent module)

## Open and set pom.xml correctly to start coding

<?xml version="1.0" encoding="UTF-8"?>

<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>

  <groupId>br.com.siomara</groupId>
  <artifactId>fraud-check-service</artifactId>
  <version>1.0-SNAPSHOT</version>

  <name>fraud-check-service</name>
  <!-- FIXME change it to the project's website -->
  <!--<url>http://www.example.com</url> -->
  <url>https://www.siomara.com.br</url>

  <properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <maven.compiler.source>18</maven.compiler.source>
    <maven.compiler.target>18</maven.compiler.target>
    <spring.boot.maven.plugin.version>2.5.7</spring.boot.maven.plugin.version>
    <spring.boot.dependencies.version>2.5.7</spring.boot.dependencies.version>
  </properties>

  <dependencyManagement>
    <dependencies>
      <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-dependencies</artifactId>
        <version>${spring.boot.dependencies.version}</version>
        <scope>import</scope>
        <type>pom</type>
      </dependency>
    </dependencies>
  </dependencyManagement>

  <dependencies>
    <dependency>
      <groupId>org.projectlombok</groupId>
      <artifactId>lombok</artifactId>
    </dependency>
    <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-test</artifactId>
    </dependency>
    <!--<dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.11</version>
      <scope>test</scope>
    </dependency>-->
  </dependencies>

  <build>
    <pluginManagement><!-- lock down plugins versions to avoid using Maven defaults (may be moved to parent pom) -->
      <plugins>
        <plugin>
          <groupId>org.springframework.boot</groupId>
          <artifactId>spring-boot-maven-plugin</artifactId>
          <version>${spring.boot.maven.plugin.version}</version>
        </plugin>
        <!--
        &lt;!&ndash; clean lifecycle, see https://maven.apache.org/ref/current/maven-core/lifecycles.html#clean_Lifecycle &ndash;&gt;
        <plugin>
          <artifactId>maven-clean-plugin</artifactId>
          <version>3.1.0</version>
        </plugin>
        &lt;!&ndash; default lifecycle, jar packaging: see https://maven.apache.org/ref/current/maven-core/default-bindings.html#Plugin_bindings_for_jar_packaging &ndash;&gt;
        <plugin>
          <artifactId>maven-resources-plugin</artifactId>
          <version>3.0.2</version>
        </plugin>
        <plugin>
          <artifactId>maven-compiler-plugin</artifactId>
          <version>3.8.0</version>
        </plugin>
        <plugin>
          <artifactId>maven-surefire-plugin</artifactId>
          <version>2.22.1</version>
        </plugin>
        <plugin>
          <artifactId>maven-jar-plugin</artifactId>
          <version>3.0.2</version>
        </plugin>
        <plugin>
          <artifactId>maven-install-plugin</artifactId>
          <version>2.5.2</version>
        </plugin>
        <plugin>
          <artifactId>maven-deploy-plugin</artifactId>
          <version>2.8.2</version>
        </plugin>
        &lt;!&ndash; site lifecycle, see https://maven.apache.org/ref/current/maven-core/lifecycles.html#site_Lifecycle &ndash;&gt;
        <plugin>
          <artifactId>maven-site-plugin</artifactId>
          <version>3.7.1</version>
        </plugin>
        <plugin>
          <artifactId>maven-project-info-reports-plugin</artifactId>
          <version>3.0.0</version>
        </plugin>
        -->
      </plugins>
    </pluginManagement>
  </build>
</project>

