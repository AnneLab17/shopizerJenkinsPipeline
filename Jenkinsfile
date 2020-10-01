pipeline {
    agent any
    
    tools {
        maven 'maven-local'
    }

    stages {

	    stage('Deploy') {
	        steps {
	            build job: 'Shopizer_02_Integration' 
    
	        }
	    }
	    
	    	    stage('Deploy Jira') {
	        steps {
			echo 'Deploying to Production from master...'
		}
		 post {
		    always {
			jiraSendDeploymentInfo environmentId: 'PRODServer', environmentName: 'PRODServer', environmentType: 'production', serviceIds: [''], site: 'shopizer-team3.atlassian.net', state: 'successful'
			}
	       
	    
	        }
	    }
    }	
}
