pipeline {
    agent any
    
    tools {
        maven 'maven-local'
    }

    stages {

	    stage('Deploy') {
		    when {
       			branch '2.7.0'
  			 }
	        steps {
	            build job: 'Shopizer_06_Deploiement' 
		 post {
		    always {
			jiraSendDeploymentInfo environmentId: 'PRODServer', environmentName: 'PRODServer', environmentType: 'production', serviceIds: [''], site: 'shopizer-team3.atlassian.net', state: 'successful'
			}
	       }
	    
	        }
	    }
    }	
}
