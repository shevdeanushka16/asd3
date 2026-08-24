pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t tut5 .'
            }
        }

        stage('Deploy') {
            steps {
                bat 'docker stop containerut5 || exit 0'
                bat 'docker rm containerut5 || exit 0'
                bat 'docker run -d -p 5400:5000 --name containerut5 tut5'
            }
        }
    }
}
