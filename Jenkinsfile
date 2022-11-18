pipeline {
    agent any
    stages {
            stage('clone') {
            steps {
                git 'https://github.com/Sh0bhitha/java-maven-app'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn -DskipTests clean install'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit '**/target/surefire-reports/*.xml'
                }
            }
        }
        
    }

}

