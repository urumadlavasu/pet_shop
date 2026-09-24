pipeline {
    agent any

    stages {

        stage('Get the code from Git') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/urumadlavasu/pet_shop.git'
            }
        }

        stage('Build the code') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy in Tomcat') {
            steps {
                deploy(
                    adapters: [
                        tomcat9(
                            alternativeDeploymentContext: '',
                            credentialsId: '71db6306-1cdd-4b36-bdf7-6ce762fe366c',
                            path: '',
                            url: 'http://35.154.209.241:8085/'
                        )
                    ],
                    contextPath: 'LoginPage',
                    war: '**/*.war'
                )
            }
        }
    }
}
