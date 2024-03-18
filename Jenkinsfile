pipeline {
    agent any

    environment {
        DOCKER_HUB_CREDENTIALS = 'adrian21071988-&$OpJAhIwGhtdGt'
        DOCKER_IMAGE_NAME = 'adrian21071988/my-site-deploy'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the GitHub repository
                git 'https://github.com/your-username/your-repo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                // Build the Docker image
                script {
                    docker.build ("my-site/14-apline")
                }
            }
        }

       
        stage('Push to Docker Hub') {
            steps {
                // Push the Docker image to Docker Hub
                script {
                    docker.withRegistry('https://index.docker.io/v1/', DOCKER_HUB_CREDENTIALS) {
                        docker.image(my-site-deploy).push()
                    }
                }
            }
        }
    }
}