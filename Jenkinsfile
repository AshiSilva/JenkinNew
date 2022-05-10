pipeline {
   agent any
   stages {
	         stage ('GIT checkout'){
	             steps {
	                 script  {					       
					       git "https://github.com/sunilkumarg-techbrain/SampleSeleniumMavenJenkins"
		                   } 
		           }
		       }
			 stage ('Maven Test Execution'){
	             steps {
	                 script  {	
			                bat(/mvn clean install/)      
		                      }        
					} 
		          
		       }
				
			   
			 stage ('Allure Report Generation'){
			   	 
	             steps {
						 allure([
							includeProperties: false,
							jdk: '',
							properties: [],
							reportBuildPolicy: 'ALWAYS',
							results: [[path: 'target/allure-results']]
						])						     
		           }
		       }
			   			 
          }
}
