pipeline{
	agent any
	// agent { docker { image 'maven:3.6.3' }}
	// agent { docker { image 'node:13.8' }}
	environment{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"

	}
	stages {
		stage('Build'){
			steps{
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "PATH - $PATH"
				echo "Build_Number - $env.BUILD_NUMBER"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}
		stage('Test'){
			steps{
				echo "Test"
			}
		}
		stage('Integration Test'){
			steps{
				echo "Integration Test"
			}
		}
	} 
	post {
		always {
			echo 'This will always run'
		}
		success {
			echo 'This will run in success case'
		}
		failure {
			echo 'This will run in failure case'
		}
	}
}