pipeline {
 agent none
 stages{
  stage("build and SonarQube Analysis")
  {
   agent any
    steps {
	 withSonarQubeEnv('mysonarqube')
	 {
	  sh "mvn clean package sonar:sonar -Dsonar.projectKey=mysonarqube -Dsonar.projectName='mysonarqube'"
	 }
	}
  }
 }
}
