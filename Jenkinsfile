pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        script {
          sh 'dotnet build AdventureWorksApi.sln.sln'
        }
      }
    }
    stage('Docker Build') {
      steps {
        script {
          sh 'docker build -t adworks-main-api .'
        }
      }
    }
    stage('Deploy to Staging') {
      steps {
        script {
          sh 'docker-compose up --build -d'
        }
      }
    }
  }
}
