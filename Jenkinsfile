pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Akamitt009/azure-cicd-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mywebsite .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker stop mysite || true
                docker rm mysite || true
                docker run -d -p 8081:80 --name mysite mywebsite
                '''
            }
        }

    }
}
