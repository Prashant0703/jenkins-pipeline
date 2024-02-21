node {
	stage("TEST") {
		print("HELLO")
	}
	stage("RUN JOB") {
		templateRender()
	}
	stage("ARCHVE") {
		archiveArtifacts atifacts: '**'
	}

}

def templateRender() {
	//def f = readYaml file: 'test.template'
	def text = 'Dear "$firstname $lastname",\nSo nice to meet you in <% print city %>.\nSee you in ${month},\n${signed}'

	def binding = ["firstname":"Sam", "lastname":"Pullara", "city":"San Francisco", "month":"December", "signed":"Groovy-Dev"]

	def engine = new groovy.text.SimpleTemplateEngine()
	def template = engine.createTemplate(text).make(binding)
	//def binding = ["name": "Chetna"]
	//def engine = new groovy.text.SimpleTemplateEngine()
	//def template = engine.createTemplate(f).make(binding)
	//writeFile(file: 'test.yaml', text: template.toString())
	println template.toString()
}
