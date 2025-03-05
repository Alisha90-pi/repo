pipeline {
 agent none
 stages{
  stage("build and SonarQube Analysis")
  {
   agent any
    steps {
	 withSonarQubeEnv('mysonarqube')
	 {
	  sh "mvn clean verify sonar:sonar \
  -Dsonar.projectKey=Jenkinsproject \
  -Dsonar.projectName='Jenkinsproject' \
  -Dsonar.host.url=http://34.58.252.102:9000 \
  -Dsonar.token=sqp_c947672d657ea0391d2762b89ab5c34b794002d0"
	 }
	}
  }
 }
}
