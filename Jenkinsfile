pipeline {
	agent {
		label 'master'
	}
	options {
		buildDiscarder(logRotator(numToKeepStr:'10'))
		disableConcurrentBuilds()
	}    
    triggers {
 		pollSCM('''# Pool SCM every 5 minutes
H/5 * * * 1-5'''
 		)
 	}
	stages {
        stage('build') {
            steps {
                script {
                    sh label: 'mvn build', script: "mvn -B clean install"
                }
            }
        }
    }
}


	
