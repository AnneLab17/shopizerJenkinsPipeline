pipeline {
    agent any
    
    tools {
        maven 'maven-local'
    }

    stages {

	    stage('Deploy') {
	        steps {
	            build job: 'Shopizer_06_Deploiement' 
    
	        }
	    }
	    
	    	    stage('Deploy Jira') {
	        steps {
			echo 'Deploying to Production from master...'
		 post {
		    always {
			jiraSendDeploymentInfo environmentId: 'PRODServer', environmentName: 'PRODServer', environmentType: 'production', serviceIds: [''], site: 'shopizer-team3.atlassian.net', state: 'successful'
			}
	       }
	    
	        }
	    }
    }	
}
