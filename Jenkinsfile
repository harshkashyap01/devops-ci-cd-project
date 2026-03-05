pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/harshkashyap01/devops-ci-cd-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop devops-app || true'
                sh 'docker rm devops-app || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 80:80 --name devops-app devops-app'
            }
        }

    }
}

