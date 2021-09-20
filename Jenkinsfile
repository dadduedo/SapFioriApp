#!/usr/bin/env groovy 

/*
 * This file bootstraps the codified Continuous Delivery pipeline for extensions of SAP solutions such as SAP S/4HANA.
 * The pipeline helps you to deliver software changes quickly and in a reliable manner.
 * A suitable Jenkins instance is required to run the pipeline.
 * More information on getting started with Continuous Delivery can be found here: https://sap.github.io/jenkins-library/
 */


pipeline { 
    agent {
        docker { image 'node:14-alpine' }
    }
    stages {
        stage('Build') { 
            steps { 
                bat 'npm -v' 
            }
        }
        stage('Test'){
            steps {
                bat 'node vars/script1.js'
            }
        }
        stage('TestDocker') {
            steps {
                sh 'node --version'
            }
        }
        stage('Deploy') {
            steps {
                bat 'npm i'
            }
        }
    }
}

// pipeline { 
//     agent any 
//     options {
//         skipStagesAfterUnstable()
//     }
//     stages {
//         stage('Build') { 
//             steps { 
//                 bat 'npm -v' 
//             }
//         }
//         stage('Test'){
//             steps {
//                 bat 'node vars/script1.js'
//             }
//         }
//         stage('Deploy') {
//             steps {
//                 bat 'npm i'
//             }
//         }
//     }
// }