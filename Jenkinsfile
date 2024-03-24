pipeline {
	agent any
	
	environment {
	        ARTIFACT_DIR = "${env.WORKSPACE}/jobs"
	}
	
	stages {
		stage("TEST") {
			print("HELLO")
			checkout scm
		}
		stage("ARCHIVE") {
			zip dir: "${env.ARTIFACT_DIR}", zipFile: 'jobs.zip', archive: true, glob: ''
		}
	}
}
