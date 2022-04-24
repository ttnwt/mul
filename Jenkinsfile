node('master')

{

stage('ContinuousDownload') 
   
	 {
	
    git 'https://github.com/ttnwt/webapp.git' 
    
	}

stage('Continuousbuild') 
   
	 {
	
   sh label: '', script: 'mvn package'
	}
}

