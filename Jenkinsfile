def dockerImage = ''

pipeline {
    environment {
        registry_url = 'asia-southeast2-docker.pkg.dev/rect-devops-training/rectgistry/'
        app_name = 'sample-backend'
        app_version = '0.0.1'
    }

    agent any

    stages {
        stage ('Deploy Kubernetes') {
            agent {
                docker {
                    image 'bitnami/kubectl'
                    args '-e KUBECONFIG=$kubeconfig -e GOOGLE_APPLICATION_CREDENTIALS=$gke-service-account --entrypoint=""'
                }
            }
            steps {
                sh 'get nodes'
            }
        }
    }
}
