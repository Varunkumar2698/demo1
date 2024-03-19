pipeline {
	agent any
	tools {
	        maven 'Maven 3.8.1' 
   	}
	stages {
		stage ('build') {
			steps {
				sh 'mvn clean install -DskipTests'
			}
		
		}
		stage ('test') {
			steps {
				sh 'mvn test'
			}
			post {
				always {
					archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
				}
			}
		}
	
	}
}
