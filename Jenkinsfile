pipeline {
    agent any 
	stages {
		   
	    
		stage('Docker Build') {
		   
		     steps {
			    
				 sh """ docker build -t nsunil206/mytomcat . """
				 
				 }
		}
		stage('Push to DIR'){

              steps{
			  withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'sunil',
                        usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD']]) {
					
					sh """
					      docker login --username $USERNAME --password $PASSWORD
						  docker push nsunil206/mytomcat
					   """  
			  }
        } 
	}
}
}

