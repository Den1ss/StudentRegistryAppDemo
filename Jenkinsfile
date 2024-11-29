pipeline {
    agent any

    environment {
        NODE_VERSION = '20.x'
    }

    tools {
        nodejs '${NODE_VERSION}'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install dependencies') {
            steps {
                script {
                    if (isUnix()) {
                        bat 'npm install'
                    }
                    else {
                        bat 'npm install'
                    }
                }
            }
        }

        stage('Start the program and run tests') {
            steps {
                script {
                    bat 'npm start &'
                    bat 'wait-on http://localhost:8080'
                    bat 'npm test'
                }
            }
        }
    }

    post {
            always {
                echo "CI pipeline completed"
            }
        }
}