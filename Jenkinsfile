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
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "${dockerHome}/bin:${mavenHome}/bin:${env.PATH}"
	}
	stages {
		stage('Checkout') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "PATH: ${env.PATH}"
				echo "BUILD_NUMBER: ${env.BUILD_NUMBER}"
				echo "BUILD_ID: ${env.BUILD_ID}"
				echo "BUILD_URL: ${env.BUILD_URL}"
				echo "JOB_NAME: ${env.JOB_NAME}"
				echo "BUILD_TAG: ${env.BUILD_TAG}"
			}
		}
		stage('Compile') {
			steps {
				sh 'mvn clean compile'
			}
		}
		stage('Test') {
			steps {
				sh 'mvn test'
			}
		}
		stage('Integration Test') {
			steps {
				sh 'mvn failsafe:integration-test failsafe:verify'
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