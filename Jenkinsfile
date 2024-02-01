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
		stage('Checkout'){
			steps{
				sh 'mvn --version'
				sh 'docker version'
				echo "Checkout"
				echo "PATH - $PATH"
				echo "Build_Number - $env.BUILD_NUMBER"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}
		stage('Compile'){
			steps {
				echo "Compile"
				sh "mvn clean compile"
			}
		}
		stage('Test'){
			steps{
				echo "Test"
				sh "mvn test"
			}
		}
		stage('Integration Test'){
			steps{
				echo "Integration Test"
				sh "mvn failsafe:integration-test failsafe:verify"
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