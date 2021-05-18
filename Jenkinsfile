pipeline {
    agent {
        node {
            label 'workstation'
        }
    }
    environment {
        SURL = "pipeline.google.com"
    }
    stages {
        stage('Stage1') {
            environment{
                SURL = "Stage.google.com"
            }
            steps {
                sh 'echo Hello Stage1, URL = ${URL}'
            }
        }
        stage('Stage2') {
             steps {
                sh 'echo Hello Stage2, URL = ${URL}'
             }
        }
    }
    post {
        always {
            echo 'I will always say Hello again'
        }
    }

}