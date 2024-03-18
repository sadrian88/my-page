pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = credentials('adrian21071988-&$OpJAhIwGhtdGt')
    }
    stages {
        stage('Checkout') {
            steps {
                // Checkout the GitHub repository
                git 'https://github.com/sadrian88/my-page.git'
            }
        }
        stage('Build') {
            steps {
                sh 'docker build -t my-site/dp-alpine:latest .'
            }
        }
        stage('Login') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        stage('Push') {
            steps {
                sh 'docker push my-site/dp-alpine:latest'
            }
        }
    }
    post {
        always {
            sh 'docker logout'
        }
    }
}
