pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t registration:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                bat 'docker tag registration:v1 akshayarajana/registration:v1'
                bat 'docker push akshayarajana/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f C:/DevOps/Week-2/deployment.yaml'
                bat 'kubectl apply -f C:/DevOps/Week-2/service.yaml'
            }
        }
    }
}
