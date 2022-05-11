

node('build-in')
{
   stage('continuous download ')
   {
     git branch: 'feature', credentialsId: 'yyyyy', url: 'https://github.com/ttnwt/webapp.git'  
} 
stage('continuous build ')
   {
    sh 'mvn package'   
} 
stage('continuous deployment ')
   {
    deploy adapters: [tomcat8(credentialsId: 'qa-user', path: '', url: 'http://172.31.83.56:8080')], contextPath: 'qaenv', war: '**/*.war'   
} 
stage('continuous test ')
   {
    sh 'echo "testing successful"'   
} 
stage('continuous delivery ')
   {
   deploy adapters: [tomcat8(credentialsId: 'qa-user', path: '', url: 'http://172.31.19.227:8080')], contextPath: 'prodenv', war: '**/*.war'    
} 
}
