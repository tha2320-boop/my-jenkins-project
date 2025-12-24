pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // שלב זה מושך את הקוד מה-Git
                checkout scm [cite: 76]
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // בניית האימג' של האפליקציה לפי ה-Dockerfile שבתיקייה
                    sh 'docker build -t my-python-app .' [cite: 14]
                }
            }
        }

        stage('Run Unit Tests') {
            steps {
                script {
                    // הרצת הטסטים בתוך קונטיינר זמני
                    sh 'docker run --rm my-python-app pytest tests/unit' [cite: 13]
                }
            }
        }
        
        stage('Run Integration Tests') {
            steps {
                script {
                    // הרצת טסטים של אינטגרציה
                    sh 'docker run --rm my-python-app pytest tests/integration'
                }
            }
        }
    }
}
