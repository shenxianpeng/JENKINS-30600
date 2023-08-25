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
                            customWorkspace '/agent/workspace/python_39'
                            alwaysPull true
                            args "-u root:root --entrypoint=''"
                            // reuseNode true //JENKINS-53711
                        }
                    }
                    steps {
                        script {
                            sh """
                            python --version
                            pwd
                            hostname
                            git clone https://github.com/shenxianpeng/JENKINS-30600.git
                            """
                        }
                    }
                }
                stage('python:3.10') {
                    agent {
                        docker {
                            label 'docker'
                            image 'python:3.10'
                            customWorkspace '/agent/workspace/python_310'
                            alwaysPull true
                            args "-u root:root --entrypoint=''"
                            // reuseNode true //JENKINS-53711
                        }
                    }
                    steps {
                        script {
                            sh """
                            python --version
                            pwd
                            hostname
                            git clone https://github.com/shenxianpeng/JENKINS-30600.git
                            """
                        }
                    }
                }
            }
        }
    }
}
