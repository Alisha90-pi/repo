pipeline {
    tools {

    jdk 'JAVA_HOME'
	maven 'M2_HOME'
	}
	agent any 
	stages{
        
       stage('git checkout') {
            steps {
                git  'https://github.com/Alisha90-pi/repo.git'
            
                
            }
        }
        stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('test') {
            steps {
                sh 'mvn test'
            }
            }
		stage('package'){
            steps{
		sh 'mvn clean package'   
             sh "mv target /*.jar target /myweb.jar"			
        }
    }
    }
 }
