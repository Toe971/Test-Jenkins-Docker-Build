pipeline {
    agent none
    environment {
        APP_ENV = ''
        dockerImage = ''
    }

    stages {
        stage('Setup') {
            agent {
                docker {
                    image 'node:lts'
                    reuseNode true
                }
            }
            steps {
                sh 'printenv'
                sh 'node --version'
            }
        }

        stage('Mock BACKUP DEFAULT ENV TEMPLATE') {
            agent {
                docker {
                    image 'node:lts'
                    reuseNode true
                }
            }
            steps {
                sh 'printenv'
                sh 'node --version'
            }
        }
    }
}
