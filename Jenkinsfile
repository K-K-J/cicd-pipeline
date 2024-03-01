pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        script {
          checkout scm
          def customImage = docker.build("${registry}:${env.BUILD_ID}")
        }

      }
    }

    stage('activity2') {
      steps {
        sh '~/scripts/build.sh'
      }
    }

    stage('activity3') {
      steps {
        sh '~/scripts/test.sh'
      }
    }

  }
  environment {
    registry = 'https://github.com/K-chris703/cicd_jenkins'
  }
}