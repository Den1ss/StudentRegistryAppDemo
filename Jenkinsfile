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
                        sh 'npm install'
                    }
                    else {
                        sh 'npm install'
                    }
                }
            }
        }

        stage('Start the program') {
            steps {
                script {
                    sh 'npm start'
                }
            }
        }

        stage('Run tests') {
            steps {
                script {
                    sh 'npm test'
                }
            }
        }
    }
}