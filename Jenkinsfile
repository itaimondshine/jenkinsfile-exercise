pipeline {
  agent any

  environment {
    DOCKER_CERT_PATH = '/Users/itaimondshine/.docker/machine/certs'
  }
  stages {
    stage('stage 1') {

    container('node') {
        steps {
            sh 'node -v'
            sh 'npm -v'
            sh 'npm install'
            sh 'npm run build'
        }

      }
      
    }
    stage('stage 2') {
      environment {
        AAA_STAGE_LEVEL_VAR = 'stageLevel'
      }
      steps {
        sh 'echo $AAA_STAGE_LEVEL_VAR'
        sh 'env | sort'
      }
    }
    stage('stage 3') {
      steps {
        sh 'echo $AAA_STAGE_LEVEL_VAR'
        sh 'env | sort'
      }
    }
  }
}

