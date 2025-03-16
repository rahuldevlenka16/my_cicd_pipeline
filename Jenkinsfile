pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/your-username/my-java-project.git'
            }
        }

    //     stage('Build') {
    //         steps {
    //             sh 'mvn clean package -DskipTests'
    //         }
    //     }

    //     stage('Test') {
    //         steps {
    //             sh 'mvn test'
    //         }
    //     }

    //     stage('Build Docker Image') {
    //         steps {
    //             script {
    //                 sh """
    //                 docker build -t ${DOCKER_IMAGE}:${BUILD_NUMBER} .
    //                 docker tag ${DOCKER_IMAGE}:${BUILD_NUMBER} ${DOCKER_IMAGE}:latest
    //                 """
    //             }
    //         }
    //     }

    //     stage('Push Docker Image') {
    //         steps {
    //             withDockerRegistry([credentialsId: "${DOCKER_CREDENTIALS}", url: ""]) {
    //                 sh """
    //                 docker push ${DOCKER_IMAGE}:${BUILD_NUMBER}
    //                 docker push ${DOCKER_IMAGE}:latest
    //                 """
    //             }
    //         }
    //     }

    //     stage('Deploy to Minikube') {
    //         steps {
    //             script {
    //                 sh """
    //                 kubectl apply -f deployment.yaml
    //                 kubectl rollout status deployment my-java-app
    //                 """
    //             }
    //         }
    //     }
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build or deployment failed.'
        }
    }
}
