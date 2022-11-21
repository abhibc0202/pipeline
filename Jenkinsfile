pipeline {
  agent any; 
  environment {
    NAME = 'abhishek '
  }
  parameters {
  string defaultValue: 'Abhishek', description: 'job is built by', name: 'NAME'
  choice choices: ['main', 'master'], description: 'environment to deploy the application', name: 'BRANCH'
  credentials credentialType: 'com.cloudbees.plugins.credentials.impl.UsernamePasswordCredentialsImpl', defaultValue: 'git-hub', description: 'credentials', name: 'git', required: false
   file ''
  text defaultValue: '''chrome
firefox''', name: 'browsers'
  } 
  stages {
        stage ('git clone') {
            agent {
  label 'label2'
}
         steps {
            git(
            credentialsId: 'git-hub', url: 'https://github.com/abhibc0202/java1.git'
            )   
         sh '
            clean package
            '
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
 
