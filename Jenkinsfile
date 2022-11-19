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
    stages ('TEST PARALLE') {
      agent {
  label 'label2'
}
       environment {
    BROWSER1 = 'chorme '
    BROWSER2 = 'firefox'     
  }
      Parallel{
        stage ( 'TEST on chrome' ) {
           steps {
             echo "this is test stage"
             sh '''
             sleep 5
             echo " testing is done on $BROWSER1 "
             '''
           }
        }
         stage ( 'TEST on firefox' ) {
           steps {
             echo "this is test stage"
             sh '''
             sleep 5
             echo " testing is done on $BROWSER2 "
             '''
           }
        }  
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
 
