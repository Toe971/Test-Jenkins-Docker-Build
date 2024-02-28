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
                    image 'node:20'
                    reuseNode false
                }
            }
            steps {
                sh 'printenv'
                sh 'node --version'
            }
        }

        stage('Build for SGD, MYR, IDR') {
            parallel {
                stage('SGD') {
                    steps {
                        sh 'echo "Building for SGD"'
                    }
                }
                stage('MYR') {
                    steps {
                        sh 'echo "Building for MYR"'
                    }
                }
            }
        }
    }
}
