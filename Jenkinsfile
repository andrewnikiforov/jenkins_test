
pipeline{ 
    agent{ 
        label 'masterLin'
    }
    options { 
        timestamps()
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
            when {
                branch pattern: ".*dev.*", comparator: "REGEXP"
            }
    	    steps{
                sh 'printenv'
                echo "Branch is ${env.GIT_BRANCH}"
        		echo 'Hello world!'
                input 'Will you go for award?'
    	    }
    	}
        stage('Environment vars'){
            input {
                message "Should we continue?"
                ok "Yes, we should."
                parameters {
                   string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
            environment{
                MY_ENV = "${PERSON}"
            }
            when {
                environment name: 'MY_ENV', value: 'omillan'
            }
            steps{
                echo "Who proceeded = ${MY_ENV}"
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
