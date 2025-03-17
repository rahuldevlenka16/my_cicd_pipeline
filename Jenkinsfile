pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'my-java-app'
        // DOCKER_CREDENTIALS = 'dockerhub-credentials' // Jenkins credentials ID
        // KUBECTL = '/usr/local/bin/kubectl'
    }

    stages {
  
        // stage('Build') {
        //     steps {
        //         sh 'mvn clean package -DskipTests'
        //     }
        // }

        // stage('Test') {
        //     steps {
        //         sh 'mvn test'
        //     }
        // }

        // stage('Build Docker Image') {
        //     steps {
        //         script {
        //             sh """
        //             docker build -t ${DOCKER_IMAGE}:latest .
        //             """
        //         }
        //     }
        // }


        stage('Deploy to Minikube') {
            steps {
                script {
                    sh """
                    kubectl apply -f my-java-deployment.yaml
                    kubectl rollout status deployment my-java-app
                    """
                }
            }
        }
    }

    post {
        success {
            echo '✅ Build and deployment successful!'
        }
        failure {
            echo '❌ Build or deployment failed.'
        }
    }
}
