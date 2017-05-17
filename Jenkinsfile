#!groovy

pipeline
{
  agent any //specifies jenkins execution environment, executor and checks out a repository
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
