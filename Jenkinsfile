pipeline {
  agent any
  stages {
    stage('activity1') {
      steps {
        sh 'git clone https://github.com/K-K-J/cicd-pipeline ~/cicd_task/final'
        sh ''' cd ~/cicd_task/final
'''
        sh 'pwd'
        sh 'ls'
      }
    }

    stage('activity2') {
      steps {
        sh 'pwd | ls'
        sh '''sudo ~/cicd_task/final/scripts/build.sh


input message: \'enter password\', parameters: [password(defaultValue: \'jenkins123\', description:\'\', name: \'hidden\')]'''
      }
    }

    stage('activity3') {
      steps {
        sh 'cd ~/cicd_task/final/scripts/test.sh'
      }
    }

    stage('activity4') {
      steps {
        sh 'cd ~/cicd_task/final/'
        sh 'docker build -t activity#4'
      }
    }

    stage('activity5') {
      steps {
        sh 'cd ~/cicd_task/final/'
        sh 'docker push chris703/cicd_jenkins:activity#4-5'
      }
    }

  }
  environment {
    registry = 'chris703/cicd_jenkins'
  }
}