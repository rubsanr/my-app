pipeline {
  agent any

  stages {
    stage('Clone Repo') {
      steps {
        git branch: 'main', url: 'https://github.com/rubsanr/my-app.git'
      }
    }
    stage('Build Docker Image') {
      steps {
        script {
          sh 'docker build -t my-app-image .'
        }
      }
    }
    stage('Run Container') {
      steps {
        script {
          sh 'docker run -d -p 3000:3000 --name my-app my-app-image'
        }
      }
    }
  }
}
