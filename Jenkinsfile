pipeline {
    agent any

    environment {
        NODE_VERSION = '18.16.0'
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
                        sh 'npm install'
                    }
                }
            }
        }

        stage('Backend Setup') {
            steps {
                dir('server') {
                    script {
                        sh 'npm install'
                    }
                }
            }
        }

        stage('Frontend Build') {
            steps {
                dir('frontend') {
                    script {
                        sh 'npm run build'
                    }
                }
            }
        }

        stage('Frontend Lint') {
            steps {
                dir('frontend') {
                    script {
                        sh 'npm run lint'
                    }
                }
            }
        }

        stage('Backend Tests') {
            steps {
                dir('server') {
                    script {
                        sh 'echo "No tests specified yet"'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh 'echo "Deployment configuration required"'
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