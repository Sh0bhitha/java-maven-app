pipeline {
	agent {
		lable 'slave'
	}
	
	stages {
		stage(clone) {
			steps{
				git "https://github.com/Sh0bhitha/java-maven-app.git"
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
