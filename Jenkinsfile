properties([
     parameters ([
          string(
               defaultValue: '${WORKSPACE}/jobs',
               description: 'Package separated by comma you want to install',
               name: 'ARTIFACT_PATH'
          )
    ])
])
pipeline {
	agent any
	
	environment {
	        ARTIFACT_DIR = "${env.ARTIFACT_PATH}"
	}
	
	stages {
		stage("TEST") {
			steps {
				checkout scm
			}
		}
		stage("CREATE") {
			steps {
				echo "WORKSPACE: ${WORKSPACE}"
				echo "ARTIFACT_PATH: ${env.ARTIFACT_PATH}"
				echo "ARTIFACT_DIR: ${env.ARTIFACT_DIR}"
			}
		}
	}
	post("Artifact") {
		always {
			zip dir: "${env.ARTIFACT_PATH}", zipFile: 'jobs.zip', archive: true, glob: '', overwrite: true
		}
	}
}	
