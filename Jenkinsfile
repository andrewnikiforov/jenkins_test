pipeline{ 
    agent{ 
        label 'masterLin'
    }

// this block strted job when  second_job end in Success mode
//    triggers{
//        upstream (
//            upstreamProjects: 'my_folder/second_job',
//            threshold: hudson.model.Result.SUCCESS
//        )
//    }
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
