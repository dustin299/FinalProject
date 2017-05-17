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
            echo 'OpenVas Scanning...'
            sleep 10
          },
          'Web Application Scanning*':
          {
            echo 'Scanning Complete...'
            sleep 7
          },
          'SonarQube Analysis':
          {
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
