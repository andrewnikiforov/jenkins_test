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
               sh 'env'
            }
    }
    post{
    	always{
    	    cleanWs()
    	}	
    }
}
