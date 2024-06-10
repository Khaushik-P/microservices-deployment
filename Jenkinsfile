pipeline{
    agent any
    // environment {
	//     APP_NAME = "Microservice"
    //     RELEASE = "1.0.0"
    //     DOCKER_USER = "khaushik"
    //     DOCKER_PASS = 'docker'
    //     IMAGE_NAME = "${DOCKER_USER}" + "/" + "${APP_NAME}"
    //     IMAGE_TAG = "${RELEASE}-${BUILD_NUMBER}"
	//     JENKINS_API_TOKEN = credentials("")
    // }
    stages{
        stage("Git Checkout"){
            steps{
            git branch: 'api-server', credentialsId: 'f22fbe83-b5d3-4455-b4b2-84ae8952dc4c', url: 'https://github.com/Khaushik-P/microservices-deployment.git'
            }
        }
         stage("Docker build"){
            steps{
                sh 'docker build -t khaushik/api-server .'
                 sh 'docker tag api-server khaushik/api-server:latest'
                sh 'docker push khaushik/api-server'
            }
    }
}
}