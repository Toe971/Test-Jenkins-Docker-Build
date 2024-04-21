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
                    stage('PRE SGD') {
                        agent {
                            docker {
                                image 'node:20'
                                reuseNode false
                            }
                        }
                        sh 'echo "Test PARALLEL STAGES"'
                    }
                    stage('POST SGD') {
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
                        }
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
