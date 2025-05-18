pipeline {
    agent any

    environment {
        PATH = "$PATH:/usr/local/bin"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Frontend Setup') {
            steps {
                dir('frontend') {
                    script {
                        bat 'npm install'
                    }
                }
            }
        }

        stage('Backend Setup') {
            steps {
                dir('server') {
                    script {
                        bat 'npm install'
                    }
                }
            }
        }

        stage('Frontend Build') {
            steps {
                dir('frontend') {
                    script {
                        bat 'npm run build'
                    }
                }
            }
        }

        stage('Frontend Lint') {
            steps {
                dir('frontend') {
                    script {
                        bat 'npm run lint'
                    }
                }
            }
        }

        stage('Backend Tests') {
            steps {
                dir('server') {
                    script {
                        bat 'echo "No tests specified yet"'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    bat 'echo "Deployment configuration required"'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}