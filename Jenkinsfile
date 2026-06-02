pipeline {
    agent any

    stages {
        stage('Code checkout') {
            checkout scm
        }

        stage('Build Backend Image') {
            sh 'docker build -t app-backend ./backend'
        }

        stage('Build Frontend Image') {
            sh 'docker build -t app-frontend ./frontend'
        }

        stage('Stoping all') {
            sh 'docker compose down'
        }

        stage('Start') {
            sh 'docker compose up -d'
        }
    }
}
