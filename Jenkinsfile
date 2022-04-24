node('master')

{

stage('ContinuousDownload_master') 
   
	 {
	
    git 'https://github.com/ttnwt/webapp.git'
    
	}

stage('Continuousbuild_master') 
   
	 {
	
   sh label: '', script: 'mvn package'
	}
}

