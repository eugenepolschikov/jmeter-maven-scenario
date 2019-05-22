# How to create project from maven from scratch
## Maven command (applicable for windows)

> mvn archetype:generate "-DgroupId=com.jmeter.testproj"  "-DartifactId=jmeter-testproject" "-DarchetypeArtifactId=maven-archetype-quickstart" "-DinteractiveMode=false"

Please follow the manual for more details: https://www.blazemeter.com/blog/how-use-jmeter-maven-plugin

## In order to launch on latest jmeter version 5.1.1 we should explicitly point in
our root pom.xml we should use jmeter maven plugin of 2.9.0 version  .
Please see screenshot for details: https://i.imgur.com/h7BicEp.png  .


## Also to make things working correctly  -  we should update to latest maven version as well: to Apache Maven 3.6.1.  
It may be downloaded from here:  https://maven.apache.org/download.cgi    .  
After download, extract it, and update *path* environment veriable:  https://i.imgur.com/lnNYhlO.png  
And check in console that maven version is updated using command "mvn -version": https://i.imgur.com/V3c5Cxh.png  



## The way to verify that maven project is configured correctly for jmeter: 
## Launching jmeter scenario with parametrized 'threads','rampup','loopcount', 'env' and 'domain' .

Configuration details are mentioned here: 
(1) https://jmeteronthefly.blogspot.com/2018/12/pass-parameters-from-jmeter-maven-plugin.html

(2) http://www.mets-blog.com/jmeter-maven-plugin-pass-parameters/

(3) https://www.novatec-gmbh.de/en/blog/how-to-pass-command-line-properties-to-a-jmeter-testplan/

Command to launch parametrized scenario. 
! Please note: if not specified -  it will be executed by default with values set =1 (all params will be equal 1).

There are following environment options: 
> QA ; qa ; TEST ; test; ACCEPTANCE; acceptance; DEV; dev; PROD; prod; LIVE; live

So respective command to launch will look in the following way: 
> mvn clean verify "-Dthreads=3" "-Drampup=3" "-Dloopcount=3" "-Denv=QA" "-Ddomain=tnt.com"

> mvn clean verify "-Dthreads=3" "-Drampup=3" "-Dloopcount=3" "-Denv=qa" "-Ddomain=tnt.com"

> mvn clean verify "-Dthreads=3" "-Drampup=3" "-Dloopcount=3" "-Denv=TEST" "-Ddomain=tnt.com"

> mvn clean verify "-Dthreads=3" "-Drampup=3" "-Dloopcount=3" "-Denv=test" "-Ddomain=tnt.com"

> mvn clean verify "-Dthreads=3" "-Drampup=3" "-Dloopcount=3" "-Denv=ACCEPTANCE" "-Ddomain=tnt.com"

> mvn clean verify "-Dthreads=3" "-Drampup=3" "-Dloopcount=3" "-Denv=acceptance" "-Ddomain=tnt.com"

> mvn clean verify "-Dthreads=3" "-Drampup=3" "-Dloopcount=3" "-Denv=DEV" "-Ddomain=tnt.com"

> mvn clean verify "-Dthreads=3" "-Drampup=3" "-Dloopcount=3" "-Denv=dev" "-Ddomain=tnt.com"

> mvn clean verify "-Dthreads=3" "-Drampup=3" "-Dloopcount=3" "-Denv=PROD" "-Ddomain=tnt.com"

> mvn clean verify "-Dthreads=3" "-Drampup=3" "-Dloopcount=3" "-Denv=prod" "-Ddomain=tnt.com"

> mvn clean verify "-Dthreads=3" "-Drampup=3" "-Dloopcount=3" "-Denv=LIVE" "-Ddomain=tnt.com"

> mvn clean verify "-Dthreads=3" "-Drampup=3" "-Dloopcount=3" "-Denv=live" "-Ddomain=tnt.com"

=> in console output should be the following: 
https://i.imgur.com/ZrusWGP.png  



**IMPORTANT NOTE!** If environment in not correct (i.e parameter value not being recognized) -> 
then prefix 'undefined.' is added to environment.

For example:    
> mvn clean verify "-Dthreads=3" "-Drampup=3" "-Dloopcount=3" "-Denv=liveadscadfda" "-Ddomain=tnt.com"

then tests will be executed against 

> undefined.tnt.com 


## Generate dashboard HTML report after  execution
## HTML Report generation and analysis
Step by step configuration details might be found here
http://www.testautomationguru.com/jmeter-continuous-performance-testing-jmeter-maven/
and  here: https://stackoverflow.com/a/41461366/1546574 

After tests have been executed, please call the following command: 
>   mvn pre-site

and HTML dashboard report is generated and placed in this folder: 
'jmeter-testproject\target\jmeter\results\dashboard' (_mavenproj\jmeter-testproject\target\jmeter\results\dashboard_) 
html report:
https://i.imgur.com/7er1Ybv.png   
https://i.imgur.com/xlxbkXF.png
https://i.imgur.com/it7aTgd.png


  
  