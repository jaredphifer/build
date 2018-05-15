pipeline {
	agent none
	environment {
		NODE_VER = '8.1.0'
	}

	stages {
		stage ('Beginning') { agent any
			environment {
				DEPLOY_VERSION = 'stage'
			}
			steps {
				echo 'Hello World'
				sh 'echo $NODE_VER'
				echo "${env.DEPLOY_VERSION}"
			}
		}
		
		stage('Who Am I?') { agent any
			environment {
				DEPLOY_VERSION = 'prod'
			}
			steps {
				echo "${env.DEPLOY_VERSION}"
				sh 'host -t TXT pgp.michaelholley.us |akw -F \'"\' \'{print $2}\''
			}
		}



	}
}