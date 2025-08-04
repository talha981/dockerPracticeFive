@Library('Shared') _

pipeline {
    agent { label 'agent' }

    environment {
        IMAGE_NAME = "talhaha22/reactcicd-frontend"
        TAG = "latest"
    }

    stages {
        stage('Hello') {
            steps {
                script {
                    hello()
                }
            }
        }

        stage('Clone Repo') {
            steps {
                script {
                    cloneRepo('master', 'https://github.com/talha981/dockerPracticeFive.git')
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    buildDocker(IMAGE_NAME, TAG)
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    pushDocker(IMAGE_NAME, TAG, 'dockerHubCred')
                }
            }
        }

        stage('Deploy App') {
            steps {
                script {
                    deployApp()
                }
            }
        }
    }
}
