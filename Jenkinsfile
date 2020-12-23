pipeline {
	agent any
	// agent { docker { image 'maven:latest' }}
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
		stages {
			stage('Checkout') {
				steps {
					echo "Build"
					echo "PATH - $PATH"
					sh "mvn --version"
					sh "docker version"
	
					echo "BUILD_NUMBER - $env.BUILD_NUMBER"
					echo "BUILD_ID - $env.BUILD_ID"
					echo "BUILD_NAME - $env.JOB_NAME"
					echo "BUILD_TAG - $env.BUILD_TAG"
				}
			}
			stage('Compine') {
					steps {
						sh "mvn clean compile"
				}
			stage('Test') {
					steps {
						sh "mvn test"
				}
			}
			stage('Integration Test') {
					steps {
						echo "mvn failsafe:integration-test failsafe:verify"
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