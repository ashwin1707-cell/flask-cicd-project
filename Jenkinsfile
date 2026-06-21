pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/ashwin1707-cell/flask-cicd-project.git'
            }
        }

        stage('Build Image') {
            steps {
                sh 'docker build -t ashwin0717/flask-app:v3 .'
            }
        }

        stage('Push Image') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-creds',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {
                    sh '''
                    echo "$DOCKER_PASS" | docker login -u "$DOCKER_USER" --password-stdin
                    docker push ashwin0717/flask-app:v3
                    '''
                }
            }
        }

    }
}