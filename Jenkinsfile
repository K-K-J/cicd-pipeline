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
        sh '''pwd 
cd ~/cicd_task/final/scripts/ && ls -la && chmod +x build.sh && ./build.sh'''
        sh '''sudo ~/cicd_task/final/scripts/build.sh

'''
      }
    }

    stage('activity3') {
      steps {
        sh 'cd ~/cicd_task/final/scripts/ && chmod +x test.sh && ./test.sh'
      }
    }

    stage('activity4') {
      steps {
        sh 'cd ~/cicd_task/final/ && ls'
        sh 'docker build -t activity4-5 .'
      }
    }

    stage('activity5') {
      steps {
        sh 'cd ~/cicd_task/final/'
        sh 'docker push chris703/cicd_jenkins:activity4-5'
      }
    }

  }
  environment {
    registry = 'chris703/cicd_jenkins'
  }
}