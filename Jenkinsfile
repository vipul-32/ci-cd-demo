pipeline {
  agent any
  tools {
      go 'gotest'
  }
  environment {
      GO111MODULE='on'
  }
  
  stages {
    stage('Test') {
      steps {
        git 'https://github.com/vipul-32/ci-cd-demo.git'
        sh 'go test ./...'
      }
    }
    stage('Build') {
        steps {
        git 'https://github.com/vipul-32/ci-cd-demo.git'
        sh 'go build .'
        }
    }
    stage('Run') {
        steps {
            sh 'cd /var/lib/jenkins/workspace/full-cicd-go && go-webapp-sample &'
        }
    }

  }
}
