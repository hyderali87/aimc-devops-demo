pipeline {
    agent any

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
