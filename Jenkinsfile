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

    stage('Deploy to Tomcat ') {
      steps {
        sh 'cp target/devops.war /opt/tomcat9/apache-tomcat-9.0.64/webapps/'
      }
    }

  }
}