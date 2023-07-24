pipeline{ 
         agent { label "aws-node1" }
		 stages {
		    stage("checkout code") {
		      steps {
		       git 'https://github.com/cloud-dev-user/war-demo-app.git'
		           }
            }
		    stage("build code") {
		     steps {
		         sh "mvn install" 
		         }
            }  
		 }
        }
