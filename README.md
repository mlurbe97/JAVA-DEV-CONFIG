# JAVA-DEV-CONFIG

## Author

* Manel Lurbe Sempere (manellurbe@gmail.com)

## Readme Content

<!--ts-->
* [Content](#Readme-Content)
    1. [UBUNTU BASED](#1-UBUNTU-BASED)
        * [JAVA JDK](#1I-JAVA-JDK)
        * [APACHE MAVEN](#1II-APACHE-MAVEN)
        * [APACHE TOMCAT](#1III-APACHE-TOMCAT)
    2. [WINDOWS BASED](#2-WINDOWS-BASED)
        * [JAVA JDK](#2I-JAVA-JDK)
        * [APACHE MAVEN](#2II-APACHE-MAVEN)
        * [APACHE TOMCAT](#2III-APACHE-TOMCAT)

## 1. UBUNTU BASED


### 1.I. JAVA JDK

- Uninstall the open-jdk:
    ```
    sudo apt-get update && sudo apt-get remove openjdk*
    ```

- Get JAVA JDK from oracle and decompress:
    ```
    tar -zxvf jdk*.tar.gz
    ```

- Place it into the folder:
    ```
    sudo mv jdk*/ /usr/lib/jvm/
    ```

- Install the java alternatives:
    ```
    sudo update-alternatives --install "/usr/bin/java" "java" "/usr/lib/jvm/jdk-21.0.3/bin/java" 0
    sudo update-alternatives --set java /usr/lib/jvm/jdk-21.0.3/bin/java
    ```

- Install the javac alternatives:
    ```
    sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/lib/jvm/jdk-21.0.3/bin/javac" 0
    sudo update-alternatives --set javac /usr/lib/jvm/jdk-21.0.3/bin/javac
    ```

- In /etc/environment:
    ```
    sudo nano /etc/environment
    ```

    - Define JAVA_HOME:
        ```
            PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin"
            JAVA_HOME="/usr/lib/jvm/jdk-21.0.3"
        ```

- Refresh the environment:
    ```
    source /etc/environment
    ```

- Check Java compiler version:
    ```
    javac -version
    ```
    - Correct output example:
        ```
        javac 21.0.3
        ```

- Check Java VM version:
    ```
    java -version
    ```
    - Correct output example:
        ```
        java version "21.0.3" 2024-04-16 LTS
        Java(TM) SE Runtime Environment (build 21.0.3+7-LTS-152)
        Java HotSpot(TM) 64-Bit Server VM (build 21.0.3+7-LTS-152, mixed mode, sharing)
        ```

### 1.II APACHE MAVEN

- Download [Apache Maven](https://maven.apache.org/download.cgi) and decompress:
    ```
    tar -zxvf apache-maven-*.tar.gz
    ```

- Install Apache Maven on this folder:
   ```
    sudo mkdir /opt/apache-maven
    sudo chown user:user /opt/apache-maven/
    mv apache-maven-*/* /opt/apache-maven/
    ```

- In /etc/environment:
    ```
    sudo nano /etc/environment
    ```

    - Define MAVEN_HOME:
        ```
            PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/opt/apache-maven/bin"
            JAVA_HOME="/usr/lib/jvm/jdk-21.0.3"
            MAVEN_HOME="/opt/apache-maven"
        ```

- Refresh the environment:
    ```
    source /etc/environment
    ```

- Check Maven version:
    ```
    mvn --version
    ```

    - Correct output example:
        ```
        Apache Maven 3.9.6 (bc0240f3c744dd6b6ec2920b3cd08dcc295161ae)
        Maven home: /opt/apache-maven Java version: 21.0.3, vendor: Oracle Corporation,
        runtime: /usr/lib/jvm/jdk-21.0.3
        Default locale: es_ES, platform encoding: UTF-8
        OS name: "linux", version: "6.8.0-35-generic", arch: "amd64", family: "unix"
        ```

### 1.III APACHE TOMCAT

- Download [Apache Tomcat](https://tomcat.apache.org/) and decompress:
    ```
    tar -zxvf apache-tomcat-*.tar.gz
    ```

- Install Apache Tomcat on this folder:
    ```
    sudo mkdir /opt/apache-tomcat
    sudo chown user:user /opt/apache-tomcat/
    mv apache-tomcat-*/* /opt/apache-tomcat/
    ```

- In /etc/environment:
    ```
    sudo nano /etc/environment
    ```

    - Define CATALINA_HOME:
        ```
            PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/opt/apache-maven/bin:/opt/apache-tomcat/bin"
            JAVA_HOME="/usr/lib/jvm/jdk-21.0.3"
            MAVEN_HOME="/opt/apache-maven"
            CATALINA_HOME="/opt/apache-tomcat"
        ```
- Refresh the environment:
    ```
    source /etc/environment
    ```

- Check Maven version:
    ```
    catalina.sh version
    ```

    - Correct output example:
        ```
        Using CATALINA_BASE:   /opt/apache-tomcat
        Using CATALINA_HOME:   /opt/apache-tomcat
        Using CATALINA_TMPDIR: /opt/apache-tomcat/temp
        Using JRE_HOME:        /usr/lib/jvm/jdk-21.0.3
        Using CLASSPATH:       /opt/apache-tomcat/bin/bootstrap.jar:/opt/apache-tomcat/bin/tomcat-juli.jar
        Using CATALINA_OPTS:   
        Server version: Apache Tomcat/10.1.25
        Server built:   Jun 14 2024 19:31:59 UTC
        Server number:  10.1.25.0
        OS Name:        Linux
        OS Version:     6.8.0-35-generic
        Architecture:   amd64
        JVM Version:    21.0.3+7-LTS-152
        JVM Vendor:     Oracle Corporation
        ```

## 2. WINDOWS BASED

### 2.I. JAVA JDK

### 2.II. APACHE MAVEN

### 2.III. APACHE TOMCAT