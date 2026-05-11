pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/Akamitt009/azure-cicd-project.git'
            }
        }

        stage('Deploy Website') {
            steps {
                sh '''
                mkdir -p /var/www/html
                rm -rf /var/www/html/*
                cp -r images index.html README.md Dockerfile Jenkinsfile /var/www/html/
                '''
            }
        }

    }
}
