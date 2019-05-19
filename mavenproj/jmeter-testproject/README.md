# How to create project from maven from scratch
## Maven command (applicable for windows)

> mvn archetype:generate "-DgroupId=com.jmeter.testproj"  "-DartifactId=jmeter-testproject" "-DarchetypeArtifactId=maven-archetype-quickstart" "-DinteractiveMode=false"

## In order to launch on latest jmeter version 5.1.1 we should explicitly point in
our root pom.xml we should use jmeter maven plugin of 2.9.0 version  .
Please see screenshot for details: https://i.imgur.com/h7BicEp.png  .


## Also to make things working correctly  -  we should update to latest maven version as well: to Apache Maven 3.6.1.  
It may be downloaded from here:  https://maven.apache.org/download.cgi    .  
After download, extract it, and update *path* environment veriable:  https://i.imgur.com/lnNYhlO.png  
And check in console that maven version is updated using command "mvn -version": https://i.imgur.com/V3c5Cxh.png  


## The way to verify that maven project is configured correctly for jmeter: 

>     mvn clean verify  

=> in console output should be the following: 
https://i.imgur.com/ZrusWGP.png  



