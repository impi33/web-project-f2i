pipeline {
	agent any
	
	stages {
		stage('Init') {
			steps {
			echo "Testing..."
			}
		}
		stage('Build') {
			steps {
				bat 'mvn clean package'
			}
			post {
				success {
					echo 'Now Archiving..'
					archiveArtifacts artifacts: '**/target/*.war'
				}
			}
		}
		stage ('deploy-stage') {
			steps {
				build job: 'deploy-stage'
			}
		}
	}
}


