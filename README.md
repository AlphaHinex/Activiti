Activiti
========

[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.activiti/activiti-engine/badge.svg)](https://maven-badges.herokuapp.com/maven-central/org.activiti/activiti-engine)

Homepage: http://activiti.org/


Activiti is a light-weight workflow and Business Process Management (BPM) Platform targeted at business people, developers and system admins. Its core is a super-fast and rock-solid BPMN 2 process engine for Java. It's open-source and distributed under the Apache license. Activiti runs in any Java application, on a server, on a cluster or in the cloud. It integrates perfectly with Spring, it is extremely lightweight and based on simple concepts.

Activiti JIRA: https://activiti.atlassian.net

Activiti QA: http://ec2-54-217-5-246.eu-west-1.compute.amazonaws.com:8080/jenkins/


web-designer-v6 branch
----------------------

This branch use `Gradle` build system to pack Activiti front-end static resources from `activiti-app` module into `activiti-web-designer-xxx.jar` as `Acitiviti Web Designer`.

Static resources are packed under `META-INF/resources/` in the jar, which could be used as a dependency of the main web app.

### Current version

Now this branch has merged [activiti-6.0.0](https://github.com/Activiti/Activiti/tree/activiti-6.0.0) tag, and you can find diff [here](https://github.com/Activiti/Activiti/compare/activiti-6.0.0...propersoft-cn:web-designer-v6)

### How to use

Clone this repo and add upstream, you should only do this once:

    $ git clone https://github.com/propersoft-cn/Activiti.git
    $ cd Activiti
    $ git remote add upstream https://github.com/Activiti/Activiti.git

Merge with Activiti release every time you want to update your jar

    $ git checkout master
    $ git pull upstream activiti-x.xx.x
    $ git checkout web-designer-v6
    $ git merge master
    # change version string in jar filename
    $ vi modules/activiti-ui/activiti-app/build.gradle

and then pack with

    $ ./gradlew clean pack

and you could find the `activiti-web-designer-xxx.jar` at `modules/activiti-ui/activiti-app/build/libs`
