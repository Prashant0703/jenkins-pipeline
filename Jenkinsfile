properties([
     parameters ([
          string(
               defaultValue:  '${WORKSPACE}/jobs',
               description: 'Package separated by comma you want to install',
               name: 'ARTIFACT_PATH'
          )
    ])
])
pipeline {
	agent any
	
	environment {
	        ARTIFACT_DIR = "${env.WORKSPACE}/jobs"
	}
	
	stages {
		stage("TEST") {
			steps {
				echo "WORKSPACE: ${env.WORKSPACE}"
				echo "ARTIFACT_PATH: ${env.ARTIFACT_PATH}"
				checkout scm
			}
		}
		// stage("ARCHIVE") {
		// 	steps {
		// 		zip dir: "${env.ARTIFACT_DIR}", zipFile: 'jobs.zip', archive: true, glob: ''
		// 	}
		// }
	}
	post("Artifact") {
		always {
			zip dir: "${env.ARTIFACT_PATH}", zipFile: 'jobs.zip', archive: true, glob: '', overwrite: true
		}
	}
}	
