pipeline {
    agent {
        node {
            label 'workstation'
        }
    }
    stages {
        stage('Stage1') {
            steps {
                sh 'echo Hello Stage1'
            }
        }
        stage('Stage2') {
             steps {
                sh 'echo Hello Stage2'
             }
        }
    }
}