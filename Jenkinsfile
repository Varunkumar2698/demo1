pipeline {
	agent {
		label 'Node_1'
	}
	tools {
	        maven 'maven 3.8.1' 
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
