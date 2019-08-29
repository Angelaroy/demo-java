pipeline {
  agent {
    dockerfile {
      filename 'docker/Dockerfile'
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
