pipeline {
  agent {
    node {
      label 'node_1.4'
    }

  }
  stages {
    stage('CI stage ') {
      steps {
        sh 'mvn clean deploy'
      }
    }

    stage('Download package') {
      steps {
        withCredentials([usernamePassword(credentialsId: \'nexus-cred\', passwordVariable: \'nx_pass\', usernameVariable: \'nx_user\')]) {
 
  sh "wget --http-user=${nx_user} --http-password=${nx_pass} http://192.168.1.4:8081/repository/maven-snapshots/learnwell/com/devops/1.0-SNAPSHOT/devops-1.0-20220923.151629-1.war"
   
}
        }
      }

    }
  }
