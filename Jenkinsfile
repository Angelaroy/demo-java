pipeline {
  agent {
    dockerfile {
      filename './Dockerfile'
    }
  }
  stages {
    stage('compile') {
      steps {
        bat label: '', script: 'mvn package'
      }
    }
}
}
