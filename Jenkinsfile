pipeline{ 
    agent{ 
        label 'masterLin'
    }
    options { 
        timestamps()
    }
    stages{
    	stage('Hello stage'){
            when {
                expression{
                    return env.GIT_BRANCH == 'origin/developf'
                }
            }
    	    steps{
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
                expression {
                    return env.MY_ENV == 'omillan'
                }
            }
            steps{
                sh 'printenv'
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
