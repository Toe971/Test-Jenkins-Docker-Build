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

        stage('Parallel Build for SGD, MYR, IDR') {
            failFast true
            parallel {
                stage("SGD") {
                        agent {
                            docker {
                                image 'node:20'
                                reuseNode false
                            }
                        }
                        steps {
                            sh 'echo "Building for SGD"'
                            sh 'sleep 20s'
                            sh 'echo `date`'
                            sh 'echo "Test PARALLEL STAGES SGD SLEEP"'
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
                        sh 'echo `date`'

                    }
                }
            }
        }
    }
}
