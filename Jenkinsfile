pipeline {
  agent any
  stages {
    stage('activity2') {
      steps {
        sh ' sudo scripts/build.sh'
      }
    }

    stage('activity3') {
      steps {
        sh 'sudo scripts/test.sh'
      }
    }

  }
  environment {
    registry = 'https://github.com/K-chris703/cicd_jenkins'
  }
}