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
    stage('Automated Security testing')
    {
      steps
      {
        echo 'Running SonarQube....'
        sleep 5
      }
      steps
      {
        echo 'Running Web Application Scanner.....'
        sleep 5
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
}
