pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git url: 'https://github.com/appasabkambale/workhive-devops.git', branch: 'main'
            }
        }

        stage('Build Docker Images') {
            steps {
                sh 'docker build -t workhive-client -f Dockerfile.client .'
                sh 'docker build -t workhive-server -f Dockerfile.server .'
            }
        }

        stage('Run Selenium Tests') {
            steps {
                // Replace with your test script
                sh './run-selenium-tests.sh'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}
