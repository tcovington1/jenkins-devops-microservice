pipeline {
	// agent any
	agent { docker { image 'maven' }}
		stages {
			stage('Build') {
				steps {
					echo "Build"
					sh 'mvn --version'
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