pipeline {
    agent any

    tools {
        jdk 'Java 21'           // ✅ Use the name from Step 1
        maven 'Maven 3.9.9'   // ✅ Already working fine
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
        failure {
            echo '❌ Build failed!'
        }
        success {
            echo '✅ Build succeeded!'
        }
    }
}
