pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/varshalahane2004-ops/CI-CD-Final-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t devops-app .'
            }
        }

        stage('Deploy Website') {
            steps {
                bat 'docker stop devops || exit 0'
                bat 'docker rm devops || exit 0'
                bat 'docker run -d --name devops -p 8086:80 devops-app'
            }
        }
    }
}