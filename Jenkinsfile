pipeline {
	agent any
	
	stages {
		stage(clone) {
			steps{
				git "https://github.com/ravichandra9594/java-maven-app-karthik.git"
			}
		}
		stage(build) {
			steps{
				sh "mvn clean install -DskipTests"
			}
		}
		stage(test) {
			steps{
				sh "mvn test"
			}
			post {
				always {
					  junit "target/surefire-reports/*.xml"
					  archiveArtifacts 'target/*.jar'
				}
			}
		}
		
	}
}
