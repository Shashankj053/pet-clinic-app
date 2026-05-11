pipeline {
    agent any

    stages {

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