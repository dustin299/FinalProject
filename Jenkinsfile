#!groovy

pipeline
{ 
  agent any //specifies jenkins execution env, executor and checks out a repository
  }
  
 stages //list of stages specifying in which stage the pipeline steps will be executed.
 {
  
 //*********************************
  stages('Initialization')
  {
    steps
    {
      echo 'Task Initialization...'
      sleep 5
      }
      
  //********************************
  stages('Build')
  {
    steps
    {
      echo 'Starting Build Process....'
      sleep 5
      }
      
   //*************************************
   //Skipping other process and jumping to Security Testing for Demo
   stages('Automated Security Testing')
   {
    steps
    {
      echo 'Starting Code Scanning using SonarQube....'
      sleep 5
      }
      
    steps
    {
      echo 'Starting Web Application Scanner using ....'
      sleep 5
      }
      
     steps
     {
     echo 'Starting Infrastructure Scanning using ...'
     }
     
   //************************************
   stages('Complete')
   {
    steps
    {
      echo 'Pipeline is complete...'
      sleep 5
      }
   }
}

   
   
   
   
   
