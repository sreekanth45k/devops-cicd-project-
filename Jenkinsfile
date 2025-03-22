pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/sreekanth45k/devops-cicd-project-.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t sreekanth45k/cicd-app:latest .'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                withDockerRegistry([credentialsId: 'sreekanth45k', url: '']) {
                    sh 'docker push sreekanth45k/cicd-app:latest'
                }
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s-deployment.yaml'
            }
        }
    }
}

