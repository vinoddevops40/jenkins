pipeline {
    agent {
        node {
            label 'workstation'
        }
    }

    options {
        disableConcurrentBuilds()
        buildDiscarder(logRotator(numToKeepStr: '6'))
    }

    environment {
        SURL = "pipeline.google.com"
        CREDS = credentials('CENTOS')
    }
    stages {
        stage('Stage1') {
            environment{
                SURL = "Stage.google.com"
            }
            steps {
                sh 'echo Hello Stage1, URL = ${SURL} , CREDS = ${CREDS}'
            }
        }
        stage('Stage2') {
             steps {
                sh 'echo Hello Stage2, URL = ${SURL}'
             }
        }
    }
    post {
        always {
            echo 'I will always say Hello again'
        }
    }

}