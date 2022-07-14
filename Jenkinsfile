pipeline {
  agent { label 'dev-agent'}
 
  stages {
    stage('BuildCode'){
    steps{
     echo 'In build step'
      sh 'mvn clean install -DskipTests'
         
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
     stage("Quality gate") {
            steps {
                waitForQualityGate abortPipeline: true
            }
        }
    } //stages
  } //pipeline
