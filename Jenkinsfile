pipeline {
    agent { node { label 'docker' } }

    stages {
        stage("Build") {
            parallel {
                stage('python:3.9') {
                    agent {
                        docker {
                            label 'docker'
                            image 'python:3.9'
                            alwaysPull true
                        }
                    }
                    steps {
                        script {
                            sh """
                            python --version
                            export VERSION=3.9
                            pwd
                            hostname
                            git clone https://github.com/shenxianpeng/JENKINS-30600.git
                            echo VERSION=\$VERSION
                            """
                        }
                    }
                }
                stage('python:3.10') {
                    agent {
                        docker {
                            label 'docker'
                            image 'python:3.10'
                            alwaysPull true
                        }
                    }
                    steps {
                        script {
                            sh """
                            python --version
                            export VERSION=3.10
                            pwd
                            hostname
                            git clone https://github.com/shenxianpeng/JENKINS-30600.git
                            echo VERSION=\$VERSION
                            """
                        }
                    }
                }
            }
        }
    }
}
