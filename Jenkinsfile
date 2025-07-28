pipeline {
    agent any

    tools {
        jdk 'Java 21'
        maven 'Maven 3.9.9'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/shrirangpatil007/jenkins-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo '✅ Build successful!'
        }
        failure {
            echo '❌ Build failed!'
        }
    }
}
