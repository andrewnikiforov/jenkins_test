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
                input 'Will you go for award?'
    	    }
    	}
        stage('Environment vars'){
           steps{
                input {
                    message "Should we continue?"
                    ok "Yes, we should."
                    submitter "omillan"
                    parameters {
                        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                    }
                }
               echo "${currentBuild.number}"
            }
        }
    }
    post{
    	always{
    	    cleanWs()
    	}	
    }
}
