pipeline{
    agent any
    stages{
        stage("Git Checkout"){
            git branch: 'email-service', credentialsId: 'f22fbe83-b5d3-4455-b4b2-84ae8952dc4c', url: 'https://github.com/Khaushik-P/microservices-deployment.git'
        }
    }
}