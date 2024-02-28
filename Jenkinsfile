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
                    agent {
                        docker {
                            image 'node:20'
                            reuseNode false
                        }
                    }
                    steps {
                        sh 'echo "Building for SGD"'
                        sh 'sleep 20s'
                    }
                }
                stage('MYR') {
                    agent {
                        docker {
                            image 'node:20'
                            reuseNode false
                        }
                    }
                    steps {
                        sh 'echo "Building for MYR"'
                    }
                }
            }
        }
    }
}
