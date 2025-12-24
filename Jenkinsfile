pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps { checkout scm }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build --no-cache -t my-python-app .'
            }
        }
        stage('Run Unit Tests') {
            steps {
                sh 'docker run --rm my-python-app pytest tests/test_unit_math.py'
            }
        }
        stage('Run Integration Tests') {
            steps {
                sh 'docker run --rm my-python-app pytest tests/test_integration_api.py'
            }
        }
    }
}
