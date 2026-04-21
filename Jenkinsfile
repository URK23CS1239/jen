pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t <username>/app .'
      }
    }
    stage('Push') {
      steps {
        sh 'docker login -u <username> -p <password>'
        sh 'docker push <username>/app'
      }
    }
    stage('Run') {
      steps {
        sh 'docker run -d -p 5000:5000 <username>/app'
      }
    }
  }
}
