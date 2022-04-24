node('master')

{

stage('ContinuousDownload') 
   
	 {
	
    git 'https://github.com/ttnwt/webapp.git' 
    
	}

stage('Continuousbuild') 
   
	 {

   input message: 'Waiting for approval from executor', submitter: 'ttwnt'
   sh label: '', script: 'mvn package'
	}
}

