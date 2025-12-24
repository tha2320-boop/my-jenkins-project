pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm [cite: 76]
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t my-python-app .' [cite: 14]
                }
            }
        }

        stage('Run Unit Tests') {
            steps {
                script {
                    sh 'docker run --rm my-python-app pytest tests/unit' [cite: 13]
                }
            }
        }
        
        stage('Run Integration Tests') {
            steps {
                script {
                    sh 'docker run --rm my-python-app pytest tests/integration'
                }
            }
        }
    }
}
