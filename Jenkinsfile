pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        sh 'make check'
      }
    }
    stage('') {
      steps {
        emailext(subject: 'packager-maintenance', body: 'Check the build result.')
      }
    }
  }
  post {
    always {
      junit '**/target/*.xml'

    }

    failure {
      echo 'FAIL'

    }

  }
}