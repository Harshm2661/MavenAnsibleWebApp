pipeline{
	agent any
	environment {
		LANG = 'en_US.UTF-8'
		LC_ALL = 'en_US.UTF-8'
	}
	tools {
		maven 'Maven'
	Jenkins
	}
	stages {
		stage('Checkout') 
			steps {
				git branch: 'master',url:'https://github.com/Harshm2661/MavenAnsibleWebApp.git'
			}
		}
		stage('Build') {
			steps {
				sh 'mvn clean package'
			}
		}
		stage('Archive') {
			steps {
				archiveArtifacts artifacts: 'target/*.war,fingerprint:true
			}
		}
		stage('Deploy') {
			steps {
				sh 'mvn clean package'
				sh 'anisble-playbook ansible/playbook.yml -i anisble/hosts.ini'
			}
		}
	}
}	
