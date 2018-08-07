pipeline {
  agent any
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
        sh 'git clone https://github.com/mhawley1230/ReadyAPI---OpenWeatherMap.git'
        sh '''cd ReadyAPI---OpenWeatherMap

git pull 

cd ..'''
      }
    }
    stage('Deliver') {
      steps {
        sh 'nohup npm start >> ./logs/log_file.txt 2>&1 &'
      }
    }
  }
}