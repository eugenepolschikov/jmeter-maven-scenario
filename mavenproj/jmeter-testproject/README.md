# How to create project from maven from scratch
## Maven command (applicable for windows)

> mvn archetype:generate "-DgroupId=com.jmeter.testproj"  "-DartifactId=jmeter-testproject" "-DarchetypeArtifactId=maven-archetype-quickstart" "-DinteractiveMode=false"


## The way to verify that maven project is configured correctly for jmeter: 

>     mvn verify  

=> in console output should be the following: https://i.imgur.com/IDmeann.png



