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



## Preparation to generate report correctly
We should set in jmeter properties  (D:\projects\2019-05(bob_jmeter_maven_config)\repo\jmeter-maven-scenario\mavenproj\jmeter-testproject\target\jmeter\bin))
> jmeter.save.saveservice.output_format=csv

https://i.imgur.com/EWADf9L.png


## Generate dashboard HTML report after  execution
Step by step configuration details might be found here
http://www.testautomationguru.com/jmeter-continuous-performance-testing-jmeter-maven/
and  here: https://stackoverflow.com/a/41461366/1546574 

After tests have been executed, please call the following command: 
>   mvn pre-site

And You will be able to see  in  'jmeter-testproject\target\jmeter\results\dashboard' folder
html report: 
https://i.imgur.com/xlxbkXF.png
https://i.imgur.com/it7aTgd.png


## Launching jmeter scenario with parametrized values for 'threads','rampup','loopcount'
Configuration details are mentioned here: 
(1) https://jmeteronthefly.blogspot.com/2018/12/pass-parameters-from-jmeter-maven-plugin.html
(2) http://www.mets-blog.com/jmeter-maven-plugin-pass-parameters/
(3) https://www.novatec-gmbh.de/en/blog/how-to-pass-command-line-properties-to-a-jmeter-testplan/

Command to launch parametrized scenario. 
! Please note: if not specified -  it will be executed by default with values set =1 (all params will be equal 1).

> mvn clean verify "-Dthreads=3" "-Drampup=3" "-Dloopcount=3"
  