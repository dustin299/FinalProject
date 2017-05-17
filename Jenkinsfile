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
    
    //**********************************************
    stage('Development Automated testing')
    {
      steps
      {
        parallel
          'API Testing*':
          {
            echo 'Unit Testing Completed...'
            sleep 7
          },
          'SonarQube Analysis*'
          {
            echo 'Running SonarQube....'
            sleep 5
          },
       
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
    stage('Automated Security Testing')
    {
      steps
      {
        parallel
          'SonarQube Sanning*':
          {
            echo 'SonarQube Completed...'
            sleep 7
          },
          'Web Application Scanning*'
          {
            echo 'Running Scanner....'
            sleep 5
          },
          'Infrastructure Scanning*':
          {
            echo 'Scanning Image using OpenVAS'
            sleep 10
          }
        
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
