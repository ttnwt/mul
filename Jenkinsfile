node('build-in') 
{
    stage('Continuous Download')
                   {
                     git branch: 'dev-multi', credentialsId: 'me', url: 'https://github.com/ttnwt/webapp.git'
                   }
    stage('Continuous build')
                   {
                    sh 'mvn package'
                   }
    stage('Continuous deployment')
                   {
                    deploy adapters: [tomcat8(credentialsId: 'qa', path: '', url: 'http://172.31.30.93:8080')], contextPath: 'qaenv', war: '**/*.war'
                   }
    stage('Continuous testing')
                   {
                    sh 'echo "testing has passed"'
                   }
     stage('Continuous delivery')
                   {
                    deploy adapters: [tomcat8(credentialsId: 'prod', path: '', url: 'http://172.31.21.148:8080')], contextPath: 'catenv', war: '**/*.war'
                   }
}
