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
				  archiveArtifacts artifact:'**/target/*.war
			  }
		  }
        
	  }
   }
   
}

  