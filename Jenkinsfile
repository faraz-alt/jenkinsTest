
pipeline {
    agent any

    environment {
        KUBECONFIG = '/var/lib/jenkins/.kube/config'
    }

    stages {
        stage('Check Kubernetes Connection') {
            steps {
                sh 'kubectl config current-context'
                sh 'kubectl get nodes'
            }
        }

        stage('Check Cluster Workloads') {
            steps {
                sh 'kubectl get deployments -A'
                sh 'kubectl get pods -A'
            }
        }
    }
}
