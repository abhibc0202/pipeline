pipeline {
  agent {
  label 'label1'
}
  stages {
    stage ('BUILD') {
      steps {
        echo " this is build stage "
        git credentialsId: 'mysore', url: 'https://github.com/abhibc0202/java1.git'
      }
    }
    stage ('TEST') {
      steps {
        echo "this is test stage"
        sh "sleep 5"
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
 
