pipeline {
  agent { dockerfile true }
  triggers {
    github {
      secretToken "This is a secret text"
      events = [push]
    }
  }
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/Sujith-sunny/GitPython.git'
      }
    }
    stage('Build') {
      steps {
        sh 'docker build -t Name python_repo:us-east-1/latest'
      }
    }
    stage('Push') {
      steps {
        sh 'docker push 596264129479.dkr.ecr.us-east-1.amazonaws.com/python_repo:latest'
      }
    }
  }
}