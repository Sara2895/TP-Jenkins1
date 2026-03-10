pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'pytest'
            }
        }

        stage('Security Scan') {
            steps {
                bat 'dependency-check.bat --project "TP-Jenkins" --scan . --format HTML'
            }
        }

    }
}
