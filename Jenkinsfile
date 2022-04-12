pipeline {
    agent any 	
	environment {
		
		        PROJECT_ID = 'p001'
                CLUSTER_NAME = 'cluster-1'
                LOCATION = 'europe-west3-c'
                CREDENTIALS_ID = 'p001'		
	}
	
    stages {		   
           stage('Deploy to K8s') { 
                steps{
                   echo "Deployment started ..."
		            sh 'ls -ltr'
		            sh 'pwd'

                    step([$class: 'KubernetesEngineBuilder', projectId: env.PROJECT_ID, clusterName: env.CLUSTER_NAME, location: env.LOCATION, manifestPattern: 'deployment.yaml', credentialsId: env.CREDENTIALS_ID, verifyDeployments: true])
		            echo "Deployment Finished ..."
            }
          }
    }
}

