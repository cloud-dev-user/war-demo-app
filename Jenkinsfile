pipeline {
  agent {
    node {
      label 'node_1.4'
    }

  }
  stages {
    stage('CI stage ') {
      steps {
        sh 'mvn clean package '
      }
    }

  }
}