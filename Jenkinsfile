pipeline {
    agent any

    stages {
        stage('Setup Environment') {
            steps {
                echo 'Creating virtual environment...'
                bat '"C:\\Users\\amey sonar\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" -m venv venv'
                bat 'venv\\Scripts\\pip install -r requirements.txt'
            }
        }

        stage('Build & Test') {
            steps {
                echo 'Running ML pipeline...'
                bat 'venv\\Scripts\\python ml_pipeline.py'
            }
        }
    }

    post {
        success {
            echo 'Pipeline SUCCESS - Model validated'
        }
        failure {
            echo 'Pipeline FAILED - Check logs'
        }
    }
}