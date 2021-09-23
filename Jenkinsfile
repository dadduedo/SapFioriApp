pipeline {
    agent {
                docker { 
                    label 'windows'
                    image 'mcr.microsoft.com/powershell'
                }
    } 
    stages {
        stage('prova') { 
            steps { 
                bat 'npm -v' 
            }
        }
        stage('Build') {
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