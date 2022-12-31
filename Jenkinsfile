pipeline {
    agent none
    environment { DOCKER_CERT_PATH = '/etc/ssl/certs' }
    stages {
        stage('Back-end') {
            agent {
                docker { image 'maven:3.8.6-eclipse-temurin-11' }
            }
            steps {
                sh 'mvn --version'
            }
        }
        stage('Front-end') {
            agent {
                docker { image 'node:16.13.1-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}
