pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                git 'https://github.com/harshkashyap01/devops-ci-cd-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-cicd-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name flask-cicd-container flask-cicd-app'
            }
        }
    }
}
