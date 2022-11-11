pipeline {
	agent {
		label 'slave'
	}
	tools {
		maven 'm1'
	}
	stages {
		stage('build') {
			steps {
				sh 'mvn -B -DskipTests clean install'
			}
		}
		stage('test') {
			steps {
				sh 'mvn test'
			}
			post {
				always {
					jnuit 'target/surefire-reports/*.xml'
				}
				sucess{
					sh 'cp /var/lib/jenkins/workspace/"first multi-configuration"/slave/myslave/target/*.jar /home/shobhitha/tomcat/tomcat2/tomcat2/webapps'
				}
			}
		}
	}
}
