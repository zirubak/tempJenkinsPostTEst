pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        sh '''#!/bin/bash

echo "##JH## `cat BUILD_VERSION.txt`"
echo "##JH## `pwd`"
echo "##JH## $WORKSPACE"

'''
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