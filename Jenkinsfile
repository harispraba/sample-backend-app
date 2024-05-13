def dockerImage = ''

pipeline {
    environment {
        registry_url = 'asia-southeast2-docker.pkg.dev/rect-devops-training/rectgistry/'
        app_name = 'sample-backend'
        app_version = '0.0.1'
        KUBECONFIG = credentials('kubeconfig-file')
        GOOGLE_APPLICATION_CREDENTIALS = credentials('gke-service-account')
    }

    agent any

    stages {
        stage ('Deploy Kubernetes') {
            agent {
                docker {
                    image 'harispraba/kubectl'
                    args '--entrypoint=""'
                }
            }
            steps {
                sh 'env'
                sh 'kubectl get nodes'
            }
        }
    }
}
