// Scripted approch
// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// }

// Declative approch
pileline{
	agent any
	states{
		stage('Build'){
			step{
				echo "Build"
			}
		}
		stage('Test'){
			step{
				echo "Test"
			}
		}
		stage('Integration Test'){
			step{
				echo "Integration Test"
			}
		}
	}
}