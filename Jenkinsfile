pipeline {
  agent any; 
  environment {
    NAME = 'abhishek '
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
      Parallel {
        stage ('TEST ON CHROME') {
           steps {
             echo "this is test stage on chrome"
             sh 'sleep5'
           }
        }
         stage ('TEST on firefox') {
           steps {
             echo "this is test stage on firefox"
             sh 'sleep5'
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
 
