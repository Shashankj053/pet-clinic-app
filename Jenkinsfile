pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/Shashankj053/pet-clinic-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t petclinic-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop petclinic-app || true'
                sh 'docker rm petclinic-app || true'
                sh 'docker run -d -p 5000:5000 --name petclinic-app petclinic-app'
            }
        }
    }
}