pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Abhiroop3917/labsheet1-2025sl93006.git'
            }
        }

        stage('Build') {
            steps {
                sh 'echo Build Stage'
            }
        }

        stage('Test') {
            steps {
                sh 'python3 calculator.py'
            }
        }

        stage('Deploy') {
            steps {
                scp -i key_1.pem calculator.py ec2-user@ec2-13-60-47-147.eu-north-1.compute.amazonaws.com:/home/ec2-user/
            }
        }
    }
}
