// Scripted
// node {
	
// 	echo "Build"
// 	echo "Test"
// 	echo "Integration Test"

// }

// Declarative
pipeline {
	agent any
	// agent { docker { image 'maven:3.6.3' } }
	// agent { docker { image 'node:current-alpine3.22' } }
	stages {
		stage('Build') {
			steps {
				// sh 'mvn --version'
				// sh 'node --version'
				echo "Build"
				echo "PATH: ${env.PATH}"
				echo "BUILD_NUMBER: ${env.BUILD_NUMBER}"
				echo "BUILD_ID: ${env.BUILD_ID}"
				echo "BUILD_URL: ${env.BUILD_URL}"
				echo "JOB_NAME: ${env.JOB_NAME}"
				echo "BUILD_TAG: ${env.BUILD_TAG}"
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
			echo "I'm awesome, I will always run"
		}
		success {
			echo "I run when you are successful"
		}
		failure {
			echo "I run when you fail"
		}
	}
}