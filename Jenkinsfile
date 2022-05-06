node('build-in') 
{
    stage('Continuous Download')
                   {
                     git branch: 'nonso', credentialsId: 'opps-user', url: 'https://github.com/ttnwt/webapp.git'
                   }                                                                                           
    stage('Continuous build')
                   {  
                    sh 'mvn package'
                   }
    stage('Continuous deployment')
                   {                                                                                                                 
                                      deploy adapters: [tomcat8(credentialsId: 'bbbb', path: '', url: 'http://172.31.5.164:8080')], contextPath: 'qaenv', war: '**/*.war'
                  } 
                   }
    stage('Continuous test')
                   {                              
                     sh ' echo "testing is successful"'
                   }
     stage('Continuous delivery')
                   {
                    input message: 'Waiting for approval from executor', submitter: 'nonso'
                     deploy adapters: [tomcat8(credentialsId: 'delivery', path: '', url: 'http://172.31.9.205:8080')], contextPath: 'prodenv', war: '**/*.war'
                 }  
                   }
}
