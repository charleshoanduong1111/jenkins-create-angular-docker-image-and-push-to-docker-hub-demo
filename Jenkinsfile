pipeline {
    agent any
    tools {nodejs "node"}
    stages {
		stage('Clone repository') {     
			steps {          
              checkout scm    
            }
        }		
        stage('Build') {
            steps {
                bat 'npm install'
                docker.build("charleshoanduong1111/angular-docker-image") 
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