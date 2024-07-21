pipeline {
	agent any
	stages {
		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--nvdApiKey "176cfd53-8ad1-40bd-a460-c10570a164d6" --format HTML --format XML ', odcInstallation: 'OWASP DependencyCheck'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}