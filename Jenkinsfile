pipeline {
	agent any
	tools {
	        maven 'Maven 3.8.1' 
   	}
	stages {
		stage ('build') {
			steps {
				sh 'mvn clean package'
			}		
		}
		stage ('test') {
			steps {
				sh 'mvn clean install -DskipTests=true'
			}
			post {
				always {
					archiveArtifacts artifacts: '**/target/*.jar', followSymlinks: false
				}
			}
		}
	
	}
}
