pipeline {
  agent any; 
  environment {
    NAME = 'abhishek '
  }
  parameters {
  string defaultValue: 'Abhishek', description: 'job is built by', name: 'NAME'
  choice choices: ['main', 'master'], description: 'environment to deploy the application', name: 'BRANCH'
  } 
  stages {
    stage ('BUILD') {
      steps {
        echo " this is build stage "
        echo "$NAME"
        git credentialsId: 'mysore', url: 'https://github.com/abhibc0202/java1.git'
      }
    }
    stage ('TEST PARALLEL') {
      parallel {
        stage ('TEST ON CHROME') {
           steps {
             echo "this is test stage on chrome"
             sh "sleep 5"
           }
        }
         stage ('TEST on firefox') {
           steps {
             echo "this is test stage on firefox"
             sh "sleep 5"
           }
        }  
      } 
    }    
     
    stage ('DEPLOY') {
      steps {
        echo "this is deploy stage "
        sh "sleep 5"
      }
    }
  }
}
 
