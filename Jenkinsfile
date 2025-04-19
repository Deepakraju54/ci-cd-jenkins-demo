pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Deepakraju54/ci-cd-jenkins-demo.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t node-ci-cd-demo .'
                }
            }
        }

        stage('Post Build') {
            steps {
                echo 'Docker image built successfully!'
            }
        }
    }
}

