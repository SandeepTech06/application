pipeline {
    agent any

    stages {
        stage('Code checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Backend Image') {
            steps {
                sh 'docker build -t app-backend ./backend'
            }
        }

        stage('Build Frontend Image') {
            steps {
                sh 'docker build -t app-frontend ./frontend'
            }
        }

        stage('Stop all') {
            steps {
                sh 'docker compose down || true'
            }
        }

        stage('Start') {
            steps {
                sh 'docker compose up -d'
            }
        }
    }
}
