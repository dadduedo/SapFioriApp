pipeline {
  agent {
    docker {
      image 'docker/getting-started'
    }

  }
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

    stage('Deliver') {
      steps {
        bat 'readlink -f ./package.json'
      }
    }

  }
}