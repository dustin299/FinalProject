#!groovy

pipeline
{
  agent any //specifies jenkins execution environment, executor and checks out a repository

  options
  {
    buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '10'))
  }

  tools
  {
    maven 'Maven 3.3.9'
    jdk 'jdk8'
    //****************************************
    stage('Initialization')
    {
      steps
      {
        sh '''
          echo "PATH = ${PATH}"
          echo "M2_HOME = ${M2_HOME}"
        '''
      }
    }
  }
}
