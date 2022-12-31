pipeline {
    agent any

   stages {
        stage('Build') {
            steps {
               echo 'Building...'
            }
        }
        stage('Test') {
            when{
                expression {
                   BRANCH_NAME == 'master' || BRANCH_NAME == 'develop'
                   }
               }
            steps {
               echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'

           }

        }

     }
    post {
    always {
        //this script will be done after the build is done
            echo 'Cleaning up...'
        }

    success {
        //this script will be done if the build is successful
            echo 'Build was successful'
        }

    failure {
        //this script will be done if the build is failed
            echo 'Build failed'
        }
    }
 }