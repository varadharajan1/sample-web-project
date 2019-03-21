pipeline {
    agent any
	tools{
		name: 'LocalJava8', type: 'jdk',
		name: 'LocalMaven', type: 'maven'
	}
    stages{
        stage('Build'){
            steps {
                bat 'mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}
