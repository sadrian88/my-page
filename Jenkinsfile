pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = credentials('adrian21071988-&$OpJAhIwGhtdGt')
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the GitHub repository
                git 'https://github.com/your-username/your-repo.git'
            }
        }
    }
    
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t my-site/dp-alpine:latest .'
            }
        }
    }

    stage('Push to Docker Hub') {
        steps {
            sh 'docker push my-site/dp-alpine:latest'
        }
    }
    post {
        always {
            sh 'docker logout'
        }
    }
}    