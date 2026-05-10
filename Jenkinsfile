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
                rm -rf /var/www/html/*
                cp -r * /var/www/html/
                '''
            }
        }

    }
}
