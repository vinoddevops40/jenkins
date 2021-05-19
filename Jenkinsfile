// pipeline {
//     agent {
//         node {
//             label 'workstation'
//         }
//     }
//
//     options {
//         disableConcurrentBuilds()
//         buildDiscarder(logRotator(numToKeepStr: '6'))
//     }
//
//     parameters {
//         string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//
//         text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
//
//         booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
//
//         choice(name: 'ENV', choices: ['DEV', 'QA', 'PROD'], description: 'Pick the environment')
//
//         password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
//     }
//
//     tools {
//         nodejs 'node'
//     }
//
//     environment {
//         SURL = "pipeline.google.com"
//         CREDS = credentials('CENTOS')
//     }
//     stages {
//         stage('Stage1') {
//             when {
//                 beforeAgent true
//                 beforeInput true
//                 anyOf {
//                     environment name: 'ENV', value: 'DEV'
//                     environment name: 'ENV', value: 'QA'
//                 }
//             }
//             input {
//                 message "Do you want to approve to continue?"
//                 ok "Yes, we should."
// //                 submitter "alice,bob"
// //                 parameters {
// //                     string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
// //                 }
//             }
//             environment{
//                 SURL = "Stage.google.com"
//             }
//             steps {
//                 sh 'echo Hello Stage1, URL = ${SURL} , CREDS = ${CREDS}'
//                 sh 'npm install'
//             }
//         }
//         stage('Stage2') {
//             when {
//                 environment name: 'ENV', value: 'PROD'
//             }
//              steps {
//                 sh 'echo Hello Stage2, URL = ${SURL}'
//              }
//         }
//     }
//     post {
//         always {
//             echo 'I will always say Hello again'
//         }
//     }
//
// }

pipeline {
    agent {
        node {
            label 'workstation'
        }
    }
    stages {
        stage('Example Build') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Example Deploy') {
            options {
                lock label: 'DOCKER', quantity: 1, variable: 'deployEnv'
            }
            steps {
                echo "Deploying to ${deployEnv}"
            }
        }
    }
}