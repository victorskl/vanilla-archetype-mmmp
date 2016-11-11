# Vanilla Multi-modules Maven Project
This is a maven archetype project. You can use this project artifact to create a Multi-modules Maven Project. For example, say, create a project name `strike`. It generate the following skeleton project structure and, 

* Top level `pom.xml` file for reactor - aka project aggregator 
* 3-modules `strike-client`, `strike-common`, `strike-server` and their related `pom.xml` files
* `strike-parent-pom` is an abstract parent `pom.xml` which contains general dependency that use for all 3-modules
* Of course you can extend the project structure further! 


        tree strike
        │   .gitignore
        │   pom.xml
        │   README.md
        │
        ├───strike-client
        │   │   pom.xml
        │   │
        │   └───src
        │       ├───main
        │       │   ├───java
        │       │   │   └───com
        │       │   │       └───example
        │       │   │               HelloClient.java
        │       │   │
        │       │   └───resources
        │       └───test
        │           └───java
        │
        ├───strike-common
        │   │   pom.xml
        │   │
        │   └───src
        │       ├───main
        │       │   ├───java
        │       │   │   └───com
        │       │   │       └───example
        │       │   │               HelloCommon.java
        │       │   │
        │       │   └───resources
        │       └───test
        │           └───java
        │
        ├───strike-parent-pom
        │       pom.xml
        │
        └───strike-server
            │   pom.xml
            │
            └───src
                ├───main
                │   ├───java
                │   │   └───com
                │   │       └───example
                │   │               HelloServer.java
                │   │
                │   └───resources
                └───test
                    └───java


# Download

* It is assumed that you [already have Maven installed](https://maven.apache.org/install.html) and you are able to run `mvn -v` from your command line.
* Go to [release tab](https://github.com/victorskl/vanilla-archetype-mmmp/releases) and download the latest pre-built release version.

### Install
Note that it is one line command. Use `\` if you want to do line breaking the command. For Windows, use caret `^` for command line breaking instead.

    mvn install:install-file -Dfile=vanilla-archetype-mmmp-1.1.jar -DgroupId=com.sankholin -DartifactId=vanilla-archetype-mmmp -Dversion=1.1 -Dpackaging=jar

### Uninstall

* Just delete it from local maven repository cache. 
* Usually `/home/{username}/.m2/repository/com/sankholin` on Linux/Mac
* Or `C:\Users\{username}\.m2\repository\com\sankholin` on Windows.

# Usage
    
Change `com.example` and `strike` to reflect your new project.
    
    mvn archetype:generate -DgroupId=com.example -DartifactId=strike -DarchetypeGroupId=com.sankholin -DarchetypeArtifactId=vanilla-archetype-mmmp -DarchetypeVersion=1.0 -DinteractiveMode=false
    
    tree strike
    
    cd strike
    
    mvn clean package
    
And browse inside target directory for each module artifacts. 

# Build
You can also build from source as follow. Otherwise you can use a release package by following instruction in Download section. 

    git clone https://github.com/victorskl/vanilla-archetype-mmmp.git
    mvn clean install
