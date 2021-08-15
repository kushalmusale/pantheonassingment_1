# Assignment 1: 
### Application Under Test: https://www.demoblaze.com/ website

###### Automation framework:
###### Developed hybrid framework (combination of Data driven approach, TestNG framework and POM design pattern) using Selenium automation tool, Java as programming language and Maven build tool 

### Components of automation framework: 

###### 1.	Page classes: Separate java classes are created for every page and declared all the web elements and methods to perform different actions on web elements of the respective page
+ com.pantheon.demoblaze.base -> package contains all the page java classes 
+ DemoBlazeBase.java – contains methods to load properties file and instantiate driver object and also it is parent of all the classes
+ LoginPage.java
+ HomePage.java 
+ AddToCartPage.java
+ PlaceOrderPage.java

###### 2. Test classes: Separate test java classes are created for different test case of every page
+ com.pantheon.demoblaze.testscripts -> package contains all the test java classes
+ LoginPageTest.java
+ HomePageTest.java
+ AddToCartPageTest.java
+ PlaceOrderPageTest.java 


###### 3.	Configuration: To hold properties file which contains details about url, username, password, browser
+ com.pantheon.demoblaze.configuration -> package contains properties file (config.properties)

###### 4.	Test data: To store test data sheet  to fill the place order details
+ com.pantheon.demoblaze.testdata -> package contains test data sheet (DemoBlazeOrderDetails.xlsx)

###### 5.	Utility classes: To generate extent reports, retrieve data from excel sheet and take screenshots
+ com.pantheon.demoblaze.utilities -> package contains utility classes 
+ ReportExtentReports.java
+ TestListener.java
+ Util.java

###### 6.	Resources: To store testing.xml file
###### 7.	Reports: To store screenshots
###### 8.	Logs: To store log files
###### 9.	Driver: To store web driver .exes
###### 10.	Maven configuration file -> pom.xml to specify all the dependencies and integrate testing.xml config file 
***
### Run Selenium tests scripts from command line: 
1.	Install maven on your machine and set the maven home and path in environment variables
2.	Go to folder where maven is installed in command prompt 
3.	Use “mvn clean install” to generate, compile, and execute the jars files and “mvn test” command to run the test scripts 

***
### Run Selenium tests using Jenkins
1. Download and install jenkins on your system 
2. Open Command prompt and navigate to project home directory and Start Jenkins server
Cmd > Project_home_Directory> java -jar Jenkins.war
Jenkins runs on 8080 port
3. Open any browser and type the URL  http://localhost:8080
4. Configure Jenkins so that Jenkins can identify other tools as well like Java, Maven etc.
5. Click on > Manage Jenkins -> Click on Configure System and add Javan and Maven 

We can execute test cases in Jenkins using 4 ways
1. Execute Windows batch command 
2. Execute shell 
3. Invoke Ant
4. Invoke top level maven targets 

Execute as "Execute Windows batch command" way:
1. Create a batch file add the same batch file to Jenkins
2. Create a job in Jenkins which will execute our build -> Open Jenkins on browser (type http://localhost:8080) -> Click on the new item -> Give the Job-Name, select Build a free-style software 

project and Click on OK button -> Navigate to Advanced Project Options > Check the use custom workspace > in directory we will specify the project home directory -> Important part now specify the 

Add Build step >Click on Execute Windows batch command -> In this section please specify the batch file which we created and click on Apply and save
3. you can finally run the Build > Click on Build now  option
4. Check Build history and Console output and verify the output
5. Also Schedule your build in Jenkins for periodic execution
