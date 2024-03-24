pipeline {
	agent any
	
	environment {
	        ARTIFACT_DIR = "${env.WORKSPACE}/jobs"
	}
	
	stages {
		stage("TEST") {
			steps {
				print("HELLO")
				checkout scm
			}
		}
		stage("ARCHIVE") {
			steps {
				zip dir: "${env.ARTIFACT_DIR}", zipFile: 'jobs.zip', archive: true, glob: ''
			}
		}
	}
}	
