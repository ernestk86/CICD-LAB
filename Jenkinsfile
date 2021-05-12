pipeline {
	agent any
	tools {
		maven 'Maven35'
	}
	stages {
		stage ('Git Checkout') {
			steps {
				git 'https://github.com/ernestk86/CICD-LAB.git'
			}
		}
		stage('Maven package') {    
 			steps {      
				bat 'mvn install'    
 			}    
		}    
		stage('Test') {
 			steps {      
				bat 'mvn test'    
 			}        
 		}
		stage('Sonar Analysis') {    
			steps {      
				bat 'mvn sonar:sonar'    
 			}         
		}
		stage('Docker Build') {    
 			steps {      
				bat 'docker build -f Dockerfile -t dsrcdemo .'     
			}         
		}  
	}
}
