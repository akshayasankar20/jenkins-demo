# jenkins-demo
***INSTALLATION & BASIC JOB***

// Install Java
java -version

// Create Job
New Item
Enter name → MyFirstJob
Select Freestyle Project
Click OK

// Add Build Step
Scroll → Build Section:
Click Add Build Step
Select: Execute Windows batch command
Enter: echo Hello Jenkins
Click Save

// Run Job
Click: Build Now

// View Output
Click: Build Number → Console Output



***CONNECT JENKINS WITH GITHUB***

// Install Git
git --version

// Create GitHub Repository
Go to GitHub
Click New Repository
Add README file

// Add Credentials in Jenkins
Manage Jenkins → Credentials → Global → Add Credentials
Username - Yuvasri-S-M
Password / Token - DojaKim_4951

// Configure Git in Job
Open Job → Configure:
Scroll to Source Code Management
Select Git

Enter:
Repository URL
Select Credentials
Click Save



***AUTOMATIC BUILD (CI)***

// Enable Trigger
Go to: Job → Configure → Triggers
Select: Poll SCM
Example schedule: * * * * *



***MULTIPLE JOB PIPELINE***

// Create 3 Jobs
Job-A → Build
Job-B → Test
Job-C → Deploy

// Configure Job A
Build Step: echo Building Project A
Post-build: Select Trigger only if the project is stable
Enter: Job-B

// Configure Job B
Build Step: echo Testing Project B
Post-build: Trigger → Job-C

// Configure Job C
Build Step: echo Deploying Project C

// Install plugin
Pipeline: stage view

// Run Pipeline
Click: Job-A → Build Now
Flow: Job-A → Job-B → Job-C



***PIPELINE (CODE BASED)***

// Create Pipeline Job
Click: New Item → Pipeline → OK

// Add Pipeline Script
Scroll to Pipeline → Script:
pipeline { 
  agent any 
  stages { 
    stage('Build') { 
      steps { 
        echo 'Build Stage' 
      } 
    } 
    stage('Test') { 
      steps { 
        echo 'Test Stage' 
      } 
    } 
    stage('Deploy') { 
      steps { 
        echo 'Deploy Stage' 
      } 
    } 
  } 
}
Click Save

// Run Pipeline
Click: Build Now

// View Stage View
Click: Stage View



***JENKINSFILE (PIPELINE AS CODE)***

// Create Jenkinsfile
GitHub repo, create file: Jenkinsfile
pipeline { 
  agent any 
    stages { 
      stage('Build') { steps { echo 'Build' } } 
      stage('Test') { steps { echo 'Test' } } 
      stage('Deploy'){ steps { echo 'Deploy' } } 
    } 
}

//Configure Jenkins Job
Go to: Pipeline Job → Configure
Select: Pipeline script from SCM
SCM: Git
Enter: Repo URL, Credentials
Script Path: Jenkinsfile

// Run Job
Click: Build Now
