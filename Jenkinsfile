pipeline {
    agent any

    stages {
        stage('Get the code from Git') {
            steps {
                git branch: 'main', url: 'https://github.com/urumadlavasu/pet_shop.git'
            }
        }

        stage('Build the code') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}
