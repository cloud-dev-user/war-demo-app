pipeline {
  agent {
    node {
      label 'node_1.4'
    }
    
  }
  parameters {
  choice choices: ['DEV', 'TEST', 'PROD'], name: 'environment'
}
  stages {
    stage('CI stage ') {
      steps {
        sh 'mvn clean deploy'
      }
    }

    stage('Download package') {
      steps {
        withCredentials(bindings: [usernamePassword(credentialsId: 'nexus-cred', passwordVariable: 'nx_pass', usernameVariable: 'nx_user')]) {
          sh "wget --http-user=${nx_user} --http-password=${nx_pass} http://192.168.1.4:8081/repository/maven-snapshots/learnwell/com/devops/1.0-SNAPSHOT/devops-1.0-20220923.151629-1.war && cp devops-1.0-20220923.151629-1.war /tmp/devops.war "
        }

      }
    }

    stage('deploy to tomcat ') {
      steps {
        sh "cp /tmp/devops.war /home/kulkarav/${environment}/tomcat9/webapps/"
      }
    }

  }
}
