pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Den1ss/StudentRegistryAppDemo'
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

        stage('Start the program') {
            steps {
                script {
                    bat 'start cmd /c "npm start"'
                }
            }
        }
        stage('Run tests') {
            steps {
                script {
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