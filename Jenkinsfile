pipeline{ 
    agent{ 
        label 'masterLin'
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
