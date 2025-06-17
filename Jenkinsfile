pipeline {
    agent any

    tools {
        maven 'M3' // we will configure this in Jenkins
    }

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/BLUEOCEAN2024/HelloJenkinsDemo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Deploy (Run Spring Boot)') {
            steps {
                sh 'java -jar target/*.jar &'
            }
        }
    }
}