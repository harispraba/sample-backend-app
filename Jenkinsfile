pipeline {
    environment {
        dockerImage = ''
    }

    agent any

    stages {
        stage ('Build node') {
            agent {
                docker {
                    image 'node:20-alpine'
                    label 'node-agent'
                    args  '-v /tmp:/tmp'
                }
            }
            steps {

            }
        }
        stage('Build docker image') {
            steps {
                script{
                    dockerImage = docker.build 'sample-backend:latest'
                }
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
