pipeline {
    agent {
        node {
            label 'workstation'
        }
    }
    environment {
        URL = "pipeline.google.com"
    }
    stages {
        stage('Stage1') {
            environment{
                URL = "Stage.google.com"
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