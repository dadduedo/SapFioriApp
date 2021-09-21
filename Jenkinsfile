#!/usr/bin/env groovy 

/*
 * This file bootstraps the codified Continuous Delivery pipeline for extensions of SAP solutions such as SAP S/4HANA.
 * The pipeline helps you to deliver software changes quickly and in a reliable manner.
 * A suitable Jenkins instance is required to run the pipeline.
 * More information on getting started with Continuous Delivery can be found here: https://sap.github.io/jenkins-library/
 */
pipeline { 
    agent any
    stages {
        stage('prova') { 
            steps { 
                bat 'npm -v' 
            }
        }
        stage('Build') {
            agent {
                docker { 
                    image 'docker/getting-started'
                }
            }
            steps {
                bat 'node --version'
                bat 'npm install'
                bat 'npm run build'
            }
        }
        stage ('Deliver') {
            steps {
                bat 'readlink -f ./package.json'
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