pipeline{ 
    agent{ 
        label 'masterLin'
    }
    triggers{
        upstream (
            upstreamProjects: 'second_job',
            threshold: hudson.model.Result.SUCCESS
        )
    }
    stages{
    	stage('Hello stage'){
    	    steps{
        		echo 'Hello world!'
    	    }
    	}
        stage('Environment vars'){
            steps{
               echo "${currentBuild}"
            }
        }
    }
    post{
    	always{
    	    cleanWs()
    	}	
    }
}
