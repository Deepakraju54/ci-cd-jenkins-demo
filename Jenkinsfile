pipeline {
    agent any

    tools {
        nodejs 'NodeJS 18.0.0' // ✅ This must go here — outside "stages"
    }

    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/Deepakraju54/ci-cd-jenkins-demo.git'
            }
        }

        stage('Build using npm') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t node-ci-cd-demo .'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                    sh 'echo $PASSWORD | docker login -u $USERNAME --password-stdin'
                    sh 'docker tag node-ci-cd-demo $USERNAME/node-ci-cd-demo:v1'
                    sh 'docker push $USERNAME/node-ci-cd-demo:v1'
                }
            }
        }
    }
}
