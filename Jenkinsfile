pipeline {
	agent any {
		label 'ssh'
	}
	tools {
	        maven 'Maven 3.3.9' 
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
					junit 'target/surefire-reports/*.*xml'
					archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
				}
			}
		}
	
	}
}
