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
    }
    post{
	always{
	    cleanWs()
	}	
    }
}
