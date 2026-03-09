pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/Sara2895/TP-Jenkins.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest'
            }
        }

        stage('SCA Scan') {
            steps {
                sh 'dependency-check.sh --project "TP-Jenkins" --scan . --format HTML'
            }
        }

    }

    post {
        failure {
            echo 'Build failed due to errors or vulnerabilities'
        }
    }
}