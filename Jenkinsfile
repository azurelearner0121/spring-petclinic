pipeline {
  agent { label 'dev-agent'}
  stages {
    stage('BuildCode'){
    steps{
     echo 'In build step'
      sh 'mvn clean install'
         
    }
    }
       stage('SonarAnalysis'){
   
     steps{
        withSonarQubeEnv('sonarqubeserver') { 
        // If you have configured more than one global server connection, you can specify its name
//      sh "${scannerHome}/bin/sonar-scanner"
        sh "mvn sonar:sonar"
         
    } // substep
    
    } //steps
       } //stage
    } //stages
  } //pipeline
