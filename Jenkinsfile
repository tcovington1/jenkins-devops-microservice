pipeline {
	agent any
	// agent { docker { image 'maven:latest' }}
		stages {
			stage('Build') {
				steps {
					echo "Build"
					// sh 'mvn --version'
					echo "BUILD_NUMBER - $env.BUILD_NUMBER"
					echo "BUILD_ID - $env.BUILD_ID"
					echo "BUILD_NAME - $env.JOB_NAME"
					echo "BUILD_TAG - $env.BUILD_TAG"
				}
			}
			stage('Test') {
					steps {
						echo "Test"
				}
			}
			stage('Integration Test') {
					steps {
						echo "Integration Test"
				}
			}
		} 
		post {
			always {
				echo " I am awesome. I run always."
			}
			success {
				echo " I run when you are successful"
			}
			failure {
				echo " I run when you are a failure"
			}
		}

}