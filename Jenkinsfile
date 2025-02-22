pipeline {
    tools {

    jdk 'JAVA_HOME_WIN'
	maven 'M2_HOME_WIN'
	}
	agent (label 'winslave')
	stages{
        
       stage('git checkout') {
            steps {
                git  'https://github.com/Alisha90-pi/repo.git'
            
                
            }
        }
        stage('compile') {
            steps {
                bat 'mvn compile'
            }
        }
        stage('test') {
            steps {
                bat 'mvn test'
            }
            }
		stage('package'){
            steps{
            bat 'mvn package'			
        }
    }
    }
 }
