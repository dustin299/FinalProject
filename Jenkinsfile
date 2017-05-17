#!groovy

pipeline
{
  agent any //specifies jenkins execution environment, executor and checks out a repository
  
  stages{
    //****************************************
    stage('Initialization')
    {
      steps
      {
          echo 'Startup Complete...'
          sleep 5
      }
    }
    
    //****************************************
    stage('Build')
    {
      steps
      {
        echo 'Building Image...'
        sleep 5
      }
    }
    
    //********************************************
     stage('Automated Scanning - DEV')
    {
      steps
      {
        parallel(
          'Code Coverage*':
          {
            echo 'Code Coverage...'
          },
          'API Testing*':
          {
            echo 'API Testing Complete...'
          },
          'SonarQube Analysis':
          {
           //sh "/var/lib/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/Default/bin/sonar-scanner -Dsonar.host.url=http://127.0.0.1:9000  -Dsonar.login=API_Key    -Dsonar.projectName=Spring-Pipeline -Dsonar.projectVersion=1.0 -Dsonar.projectKey=Sonar:spring-pipeline -Dsonar.sources=."
            
            echo 'Code Scanning Complete...'
          }
        )
      }
    }

    
     //****************************************
    stage('Clean Development Environment')
    {
      steps
      {
        echo 'Completed...'
        sleep 5
      }
    }
    
   //****************************************
    stage('Deploy to Test Environment')
    {
      steps
      {
        echo 'Deployed Image...'
        sleep 5
      }
    }
   //**********************************************
     stage('Automated Security Testing - Test')
    {
      steps
      {
        parallel(
          'Infrastructure Scanning*':
          {
            //Use OpenVAS to conduct Image Scanning #Still working on this. 
            echo 'OpenVas Scanning...'
            sleep 10
          },
          'Web Application Scanning*':
          {
            //executes Arachni to do a full scan 
            //sh /opt/arachni/bin/arachni Target_address --check=* 
            echo 'Scanning Complete...'
            sleep 7
          },
          'SonarQube Analysis':
          {
            //sh "/var/lib/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/Default/bin/sonar-scanner -Dsonar.host.url=http://127.0.0.1:9000  -Dsonar.login=API_Key    -Dsonar.projectName=Spring-Pipeline -Dsonar.projectVersion=1.0 -Dsonar.projectKey=Sonar:spring-pipeline -Dsonar.sources=."
            echo 'Code Scanning Complete...'
            sleep 5
          }
        )
      }
    }
      //**********************************************
      stage('Task Complete')
      {
        steps
        {
          echo 'Testing is Complete...'
          sleep 5
        }
      }
    }
  }
