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
      steps {
        sh 'nohup npm start >> log_file.txt 2>&1 &'
      }
    }
  }
}