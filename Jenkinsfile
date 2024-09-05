pipeline {
    agent any
    def app 
    tools {nodejs "node"}
    stages {
		stage('Clone repository') {               
              checkout scm    
        }		
        stage('Build') {
            steps {
                bat 'npm install'
                app = docker.build("charleshoanduong1111/angular-docker-image") 
            }
        }
        stage('Deliver') {
            steps {
                //bat  './jenkins/scripts/bat/deliver.bat'
                bat 'echo "Deliver passed"' 
            }
        }
    }
}