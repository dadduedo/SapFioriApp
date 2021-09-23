pipeline {
    agent any
    stages {
        stage('prova') { 
            steps { 
                bat 'npm -v' 
            }
        }
        agent {
            docker { 
                label 'windows'
                image 'mcr.microsoft.com/powershell'
            }
        } 
        stage('Build') {
            steps {
                Write-Host "hello world"
            }
        }
        stage ('Deliver') {
            steps {
                bat 'readlink -f ./package.json'
            }
        }  
    }
}