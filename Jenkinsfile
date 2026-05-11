pipeline {
    agent any

    stages {

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
