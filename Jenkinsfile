pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/hyderali87/aimc-devops-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'docker build -f docker/Dockerfile -t devops-webapp:latest .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'kubectl apply -f k8s/deployment.yaml'
                sh 'kubectl apply -f k8s/service.yaml'
            }
        }
    }
}
