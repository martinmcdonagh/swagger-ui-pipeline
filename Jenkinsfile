pipeline {
  agent {
    node {
      label 'steven'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }
    stage('Test') {
      environment {
        CI = 'true'
      }
      steps {
        sh '''cd ReadyAPI---OpenWeatherMap

git pull 

cd ..'''
      }
    }
    stage('Deliver') {
      parallel {
        stage('Deliver') {
          steps {
            sh 'npm start'
          }
        }
        stage('End Service') {
          steps {
            sleep(unit: 'SECONDS', time: 30)
            sh '''killall -9 node
'''
          }
        }
      }
    }
  }
}