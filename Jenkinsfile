pipeline {
	agent any
	tools {
		maven 'Maven'
	}
	stages {
		stage ('Git Checkout') {
			steps {
				git 'https://github.com/ernestk86/CICD-LAB.git'
			}
		}
		stage('Maven package') {    
 			steps {      
				sh 'mvn clean build'    
 			}    
		}    
		stage('Test') {
 			steps {      
				sh 'mvn test'    
 			}        
 		}
		stage('Sonar Analysis') {    
			steps {      
				sh 'mvn sonar:sonar'    
 			}         
		}
		stage('Docker Build') {    
 			steps {      
				sh 'docker build -f Dockerfile -t dsrcdemo .'     
			}         
		}  
	}
}
