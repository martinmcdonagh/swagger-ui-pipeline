pipeline {
  agent {
    node {
      label 'slave1'
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
        sh '''cd /home/ubuntu/ReadyAPI---OpenWeatherMap

git pull 

cd ..

"/home/ubuntu/SmartBear/ReadyAPI-2.4.0/bin/testrunner.sh" "-EDefault environment" "ReadyAPI---OpenWeatherMap"
'''
      }
    }
    stage('Deliver') {
      steps {
        sh 'netcat localhost 9000'
      }
    }
  }
}