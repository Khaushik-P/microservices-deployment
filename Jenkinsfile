pipeline{
    agent any
    environment {
	    APP_NAME = "microservice-email"
        RELEASE = "1.0.0"
        DOCKER_USER = "khaushik"
        DOCKER_PASS = 'docker'
        IMAGE_NAME = "${DOCKER_USER}" + "/" + "${APP_NAME}"
        IMAGE_TAG = "${RELEASE}-${BUILD_NUMBER}"
    }
    stages{
        stage("Git Checkouts"){
            steps{
            git branch: 'email-service', credentialsId: 'f22fbe83-b5d3-4455-b4b2-84ae8952dc4c', url: 'https://github.com/Khaushik-P/microservices-deployment.git'
            }
        }
        stage("Build and push to docker hub"){
            steps{
                script{
                    docker.withRegistry('',DOCKER_PASS){
                        docker_image = docker.build "${IMAGE_NAME}"
                    }
                    docker.withRegistry('',DOCKER_PASS){
                        docker_image.push("${IMAGE_TAG}")
                        docker_image.push('latest')
                    }
                }
            }
        }
    }
}