# Continuous Integration. 
Process before Continuous Integration  
![alt tag](https://github.com/spdobest/ContinuousIntegration/blob/master/Images/cicd.png)    
## Drawbacks
- NO constant Feedback
- Bug fixing - costly
- Slow software Delivery
  
## How Continuous Integration Works
![alt tag](https://github.com/spdobest/ContinuousIntegration/blob/master/Images/cicd1.png)    

## What is Continuous Integration ?
- It is a development practice where developers integrate code in a shared repository frequently, preferably several times a day.
- Each integration can then be verified by an automated build and automated tests
- One of the key benefits of integrating regularly is that you can detect errors and locate them more easily.
- Continuous deployment and continuous inDelevery have developed as best-practice for keeping your application deployle ayt any point.  
## CI CD 
- **Continuous Integration  (CI):** This is the practice of integrating changes from different developers in the team into a mainlines early as possible, in best cases several times a day. Each integration can then be verified by an automated build and automated tests.
- **Continuous Delivery (CD) :** This is the practice of keeping your codebase deployable at any point. Beyond making sure your application passes automated tests it has to have all the configuration necessary to push it into production.
Continuous Deployment : This is closely related to continuous integration and refers to keeping your application deployable at any point or even automated releasing to a test or production environment if the latest version. Passes all automated tests.
  
![alt tag](https://github.com/spdobest/ContinuousIntegration/blob/master/Images/cicd2.png)   
  
## Advantages of Continuous integration 
- Reduce risk
- Reduce overhead
- Better communication
- Earlier Detection
- Faster Iterations
- Helps Collaboration
  
## CI - principles and Practices
![alt tag](https://github.com/spdobest/ContinuousIntegration/blob/master/Images/cicd3.png)       

## Jenkins 
**What is Jenkins ??**. 
- It is the most popular open source continuous integration and continuous delivery server capable of orchestrating a chain of events / actions that helps to achieved CI in an automated fashion.
- Across Complete Life cycle : Jenkins supports the complete development lifecycle of software from building, testing, documenting the software , deployment and other stages of a software development lifecycle.
- **Jenkins Plugins :** Jenkins plugins are at the heart of how jennies functions in achieving CICD. Jenkins is interconnected with well over 1,000 plugins that allow it to integrate with most of the development, testing and deployment tools. Refer https://plugins.jenkins.io/
  
  https://github.com/spdobest/ContinuousIntegration/blob/master/Images/cicdWithJenkins4.png   

## Jenkins Distributed Architecture
https://github.com/spdobest/ContinuousIntegration/blob/master/Images/jenkins5.png   
  
- Jenkins Pipeline
- Build Pipeline
  
## Jenkins Installations 
- Install java and setup system variables
- Download Jenkins Installable and Install Jenkins (http://Jenkins.io)
- After installation complete type localhost:8080 in browser
- Go to the Jenkins installation directory and open initialAdminPassword and enter on the screen
- Authenticate First time use
- Setup and Install Jenkins Plugins
- Create First Admin user

## Advance Jenkins Installations 
- Open Jenkins.io
- Download Generic Java Package (.war file)
- Create a folder and put the downloaded .war file
- In command line extract the Jenkins.war file, java -jar Jenkins.war
- To start the Jenkins type : java -jar Jenkins.war in command line
- To change the port number just type : java -jar Jenkins.war —httpPort=8181

## Jenkins installation in TomCat 
- Download tomcat and install Tomcat
- Copy the Jenkins.war file and go to tomcat installation folder. Inside web apps folder paste the jenkins.war file
- Once you will start tomcat server, there will be a folder name called Jenkins
- After this, just type localhost:8080/jenkins in browser, it will redirect to Jenkins server
  
## Project setup  
- Create jobs in Jenkins Dashboard console

## Jenkins Dashboard and configuration
- Job/ Project : Runnable tasks that are configured in Jenkins
- Node: each machine that is part of Jenkins Grid
- Executor: Thread or slot for execution of jobs
- Build: Result got after executing a job
- Plugin: Software the extends core functionality of Jenkins
- In manage Jenkins section : you can configure your project and server

## Jenkins Users & Role management 
- Open localhost:8080
- Go to manage Jenkins
- Click Manage Users
- Create users
  
In Configure Global security system - you can accessibility of Jenkins  
  
- Add Role based Authorisation Plugins 
- Manage and assign Roles
- In manage role section, you can differentiate role user to user
  
## Creating our Jobs 
- Go to the job, select configure, you will lots of option to manage the job
- You can discard Old jobs in few days by condition
- You can set to build in timely based
  
## How to Create and Run the Job 
- Create a simple Java class and just print Hello World
```
  Class HelloWorld{
    public static void main(String…args){
      System.out.println(“Our First Jenkins Java Program”);
    }
  }
```  
- Run the project using command line
- Cd F:\javaPrograms
- Java HelloWorld.java
- Java HelloWorld
- Now create a New job in Jenkins server named HelloWorld (anyName)
- Go to Jenkins Dashboard - right click on the Helloworld Job, select Configure
- Go to Build Environment
- In Build section
-  Cd F:\javaPrograms
- Java HelloWorld.java
- Java HelloWorld
  
- Now Build the job,  go to the console and see the output
- To Trigger Builds remotely, set up
- 
  
## Job chaining 
  
## How to integrate with Remote Project(github) 
There are 2 ways integrate   
1. **Poll SCM -** Jenkins will keep polling Git to check if there are any new checkins. It will check every second if there is any changes in GitHub Project
2. **GitHub Webhook -** Jenkins will listen to a web hook & Git will let Jenkins know if there are any changes

## Poll SCM Integration 
- Go to Jenkins Dashboard, Click on Manage Jenkins
- Click on Manage Plugins
- Check if Git plugin is installed to not
- Create a repository in GitHub and push the Above HelloWorld java codes there
- Right click on the job, select configure
- Check Github
- In Source & management section, select Git and put the GitHub url there
- In Build Triggers Section, check Poll SCM
- In the build section, no need to write the Cd F:\javaPrograms
- Just write the below Two lines
- Java HelloWorld.java
- Java HelloWorld
- Now change the code inside the HelloWorld.java and push the code to GitHub repository
- After few seconds , you can see the output inside the Console output

## GitHub Webhook  Integration 
- Though localhost url is not working in Webhook
- Install ngrok in your system and create public url for the localhost url
- Now type grok http 8080 in command prompt
- It will print the global url like http://ffbcff.ngrok.op -> localhost:8080
- Once you will type localhost:4040/inspect/http in browser
- You will get two url, copy the first url and paste the url in the browser
- It will redirect to Jenkins Dashboard page
- Go to your project  GitHub repository
- Click setting, click web hook, in the Payload Url, paste the above url (something like this http://ffbcff.ngrok.op )
- The format should be like this http://ffbcff.ngrok.op/github-webhook/
- Now right click on the Job in GitHub dashboard, select configure
- In Build Triggers section check Github hook trigger for Gitscm Polling
- Now change the code in the HelloWord.java in GitHub repository. Commit and push
- Now check the Output console in Jenkins Dashboard
- You will see the output

## Which is better  
https://github.com/spdobest/ContinuousIntegration/blob/master/Images/webHookVsPollScm6.png   

## Setup Jenkins with Maven 




