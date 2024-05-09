pipeline {
    environment {
        dockerImage = ''
    }

    agent any

    stages {
        stage('Build') {
            steps {
                dockerImage = docker.build 'sample-backend:latest'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
