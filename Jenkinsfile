def gv

pipeline {
    agent any

   stages {

        stage('init') {
            steps {
                script {
                   gv = load "script.groovy"
                }
            }
        }

        stage('Build') {
            steps {

               script {
                    gv.buildApp()
               }
            }
        }
        stage('Test') {
            when{
                expression {
                   BRANCH_NAME == 'master' || BRANCH_NAME == 'deveop'
                   }

               }
            steps {
                script {
                    gv.testApp()
                }
               echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                script {
                    gv.deployApp()
                }
                echo 'Deploying...'
                echo GIT_COMMIT

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