pipeline{
	agent any
	stages {
		stage('Build'){
			steps{
				echo "Build"
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