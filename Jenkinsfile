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
                    image 'zealous_noether'
                }
            }
            steps {
                bat 'node --version'
            }
        }
        stage ('Deliver') {
            steps {
                bat 'readlink -f ./package.json'
            }
        }  
    }
}