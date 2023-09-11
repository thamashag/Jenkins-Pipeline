pipeline {
    agent any

    environment {
        DIRECTORY_PATH = '/users/thamashagalahena/dekstop/jenkinsfile'
        TESTING_ENVIRONMENT = 'testing'
        PRODUCTION_ENVIRONMENT = 'Thamasha Galahena'
    }

    stages {
        stage('Build') {
            steps {
                echo "Fetching the source code from the directory path specified by the environment variable: $DIRECTORY_PATH"
                echo "Compiling the code and generating any necessary artifacts"
            }
            post{
                success{
                    mail to: "thamasha1996@gmail.com",
                    subject: "Build status email",
                    body: "Build was successful!"

                }
            }
        }

        stage('Test') {
            steps {
                echo "Running unit tests"
                echo "Running integration tests"
            }
        }

        stage('Code Analysis') {
            steps {
                echo "Checking the quality of the code"
            }
        }

        stage('Security Scan') {
            steps {
                echo "Deploying the application to a testing environment specified by the environment variable: $TESTING_ENVIRONMENT"
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Waiting for manual approval..."
                sleep(time: 10, unit: 'SECONDS')
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Deploying the code to the production environment: $PRODUCTION_ENVIRONMENT"
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying the code to the production environment: $PRODUCTION_ENVIRONMENT"
                echo "Testing automatic trigger"
            }
        }
    }
}
