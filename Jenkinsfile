node {
	stage("TEST") {
		print("HELLO")
		checkout scm
	}
	stage("ARCHIVE") {
		archiveArtifacts artifacts: 'jobs/**'
	}

}
