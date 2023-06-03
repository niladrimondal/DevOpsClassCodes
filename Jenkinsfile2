pipeline {
    agent any

    stages {
        stage('Checkout the code') {
            steps{
                git 'https://github.com/niladrimondal/DevOpsClassCodes.git'
            }
        }
        stage('compile the code') {
            steps{
            sh 'mvn compile'
            }
        }
        stage('test the code'){
            steps{
            sh 'mvn test'
            }
        }
        stage('code quality'){
            steps{
            sh 'mvn pmd:pmd'
            }
        }
        stage('package'){
            steps{
            sh 'mvn package'
            }
        }
        stage('deploy'){
            steps{
            deploy adapters: [tomcat9(credentialsId: 'tocatpassword', path: '', url: 'http://184.72.29.240:8081/')], contextPath: 'addressbookpn', war: '**/*.war'
            }
        }
    }
}
