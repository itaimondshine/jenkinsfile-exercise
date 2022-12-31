



pipeline {



  agent {
   docker {
    image 'node:8.9.4'
   }
  }
  

  stages {
    stage('Build') {
      steps {
        sh 'npm install'
        sh 'npm run build'
      }
    }
    
    stage('Test') {
      steps {
        sh 'node --version'
      }
    }
  }
}

