pipeline {
  agent none; 
  stages {
    agent {
  label 'label1'
}
    stage ('BUILD') {
      steps {
        echo " this is build stage "
        git credentialsId: 'mysore', url: 'https://github.com/abhibc0202/java1.git'
      }
    }
    agent {
  label 'label2'
}
    stage ('TEST') {
      steps {
        echo "this is test stage"
        sh "sleep 5"
      }
    } 
     agent {
  label 'master'
}  
    stage ('DEPLOY') {
      steps {
        echo "this is deploy stage "
        sh "sleep 5"
      }
    }
  }
}
 
