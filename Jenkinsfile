def dockerImage = ''

pipeline {
    environment {
        registry_url = 'asia-southeast2-docker.pkg.dev/rect-devops-training/rectgistry/'
        app_name = 'sample-backend'
        app_version = '0.0.1'
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
                sh 'npm i'
            }
        }
        stage('Build docker image') {
            steps {
                script{
                    tag = registry_url+app_name+':'+app_version
                    dockerImage = docker.build tag
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Push to Artifact Registry') {
            steps {
                script{
                    docker.withRegistry('https://asia-southeast2-docker.pkg.dev', 'SA_KEY_AR') {
                        dockerImage.push()
                    }
                }
            }
        }
    }
}
