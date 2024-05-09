pipeline {
    environment {
        dockerImage = ''
    }

    agent any

    stages {
        stage('Build') {
            steps {
                docker.build 'sample-backend:latest'
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
