pipeline {
    tools {

    jdk 'JAVA_HOME'
	maven 'M2_HOME'
	}
	agent any 
	stages{
        
       stage('git checkout') {
            steps {
                git 'https://github.com/Alisha90-pi/repo.git'
            
                
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
                sh "mv target/*.jar target/myweb.jar"
	     }
	}
		stage("deploy"){
	   steps{

      sshagent(['test']) {

	        sh """
                 
            scp -o StrictHostKeyChecking=no target/myweb.war ec2-user@3.110.158.98:/home/ec2-user/tomcat10/webapps/

              ssh ec2-user@3.110.158.98:/home/ec2-user/tomcat10/bin/shutdown.sh
               ssh ec2-user@3.110.158.98:/home/ec2-user/tomcat10/bin/startup.sh
            
          
          """

                 }

	   
	    }
		  
	  }     
        }
    
     }

 
