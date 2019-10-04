pipeline {
   agent any 
   stages {
      stage ('Build') {
		  steps{
			  bat 'mvn clean package'
		  }
		  post  {
			  success {
				  echo 'Now archiving ...'
				  archiveArtifacts artifacts:'**/target/*.war'
			  }
		  }
        
	  }
	  stage ('Deploy to Testing') {
		  steps {
			  build job:'deploy-test'
		  }
	  }
   }
   
}

  