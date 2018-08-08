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

cd ..

"/home/ubuntu/SmartBear/ReadyAPI-2.4.0/bin/testrunner.sh" "-EDefault environment" "./ReadyAPI---OpenWeatherMap"
'''
      }
    }
    stage('Deliver') {
      steps {
        sh 'npm start'
      }
    }
  }
}