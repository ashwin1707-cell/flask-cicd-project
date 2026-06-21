pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/ashwin1707-cell/flask-cicd-project.git'
            }
        }

        stage('Build Image') {
            steps {
                bat 'docker build -t ashwin0717/flask-app:v3 .'
            }
        }

        stage('Push Image') {
            steps {
                bat 'docker push ashwin0717/flask-app:v3'
            }
        }

    }
}