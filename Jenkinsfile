pipeline {
	agent {
		label 'cicd-builder-label'
	}
	options {
		buildDiscarder(logRotator(numToKeepStr:'10'))
		disableConcurrentBuilds()
	}    
	stage('build') {
		steps {
			script {
				sh label: 'mvn build', script: "mvn -B clean install"
			}
		}
	}
}


	
