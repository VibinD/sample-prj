# nexus-common-event-schemas #

This is the repo for storing Apache Avro schemas used by the producer and consumer applications

This project is a module-based maven project and can be added more modules lates based on the needs. 

Current Modules are, 

 1. nexus-event-schema 

### 1. nexus-event-schema ###
This schema contains all the SGM related schemas currently

### How to Build this schema in Local/Dev Machine ###

Prerequisite, 
	1. Maven 3.5.0 or later 
	2. JDK 1.8

 Execute the maven command in the module or the parent 
 
 ```
 	mvn clean install
 ```
The above command will generate the java files based on the avro schema and it generate the out put jar file. 

EMOJICODE::exclamation: PLEASE DON'T PUSH THE GENERATED JAVA FILES TO THE PR. 


### Process and Steps to create new or modify the schema ###
1. Team need to create PR with the schema
2. Once the PR is merged there is Jenkin's job will kick off and deploy the artifact to Artifactory.
> **Jenkins:** https://jenkins.prod.edcore-nexus.br.internal/view/Common-Schema/
3. Once the build is finished you can find the latest release under release tab in the repo 
> **Release Tab:** : https://scm.eng.hmhco.com/Ed-Core/nexus-common-event-schemas/releases
4. The application should add the dependency to the schema

```
         <dependency>
            <groupId>com.hmhco.nexus</groupId>
            <artifactId>nexus-event-schema</artifactId>
            <version>${nexus-schema.version}</version>
        </dependency>
 ```
