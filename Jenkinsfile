pipeline {
    agent any
    
    environment {
        HOSTNAME = '192.168.100.32'
    }
    
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
                // Additional build steps if needed
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
                // Additional test steps if needed
            }
        }
        stage('Deploy') {
            steps {
                script {
                    // Use kubectl or Kubernetes CLI to deploy the application
                    sh "sed -i 's/192.168.100.32/$HOSTNAME/' deployment.yaml"
                    sh 'kubectl apply -f deployment.yaml'
                    // Additional deployment steps if needed
                }
            }
        }
    }
}