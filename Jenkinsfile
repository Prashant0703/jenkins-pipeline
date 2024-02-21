node {
	stage("TEST") {
		echo ("HELLO")
	}
	stage("RUN JOB") {
		steps {
			build job: "template-runner"
			parameters: [
			 string(name: "Name", value: "Chetna"),
			]
		}
	}
}

