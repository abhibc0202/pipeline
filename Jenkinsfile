pipeline {
  agent none; 
  environment {
    NAME = 'abhishek '
  }
  stages {
    stage ('BUILD') {
      agent {
  label 'label1'
}
      steps {
        echo " this is build stage "
        echo "$NAME"
        git credentialsId: 'mysore', url: 'https://github.com/abhibc0202/java1.git'
      }
    }
    stage ('TEST') {
      agent {
  label 'label2'
}
      steps {
        echo "this is test stage"
        sh "sleep 5"
      }
    } 
     
    stage ('DEPLOY') {
             agent {
  label 'master'
} 
      steps {
        echo "this is deploy stage "
        sh "sleep 5"
      }
    }
  }
}
 
