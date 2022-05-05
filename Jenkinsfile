node('build-in') 
{
    stage('Continuous Download')
                   {
                     git branch: 'nonso', credentialsId: 'cd', url: 'https://https://github.com/ttnwt/mul.git'
                   }
    stage('Continuous build')
                   {
                    sh 'mvn package'
                   }
    stage('Continuous deployment')
                   {
                    deploy adapters: [tomcat8(credentialsId: 'qa', path: '', url: 'http://172.31.5.164:8080')], contextPath: 'qaenv', war: '**/*.war'
                   }
    stage('Continuous testing')
                   {
                    sh 'echo "testing has passed"'
                   }
     stage('Continuous delivery')
                   {
                    input message: 'Waiting for approval from executor', submitter: 'nonso'
                    deploy adapters: [tomcat8(credentialsId: 'prod', path: '', url: 'http://172.31.9.205:8080')], contextPath: 'prodenv', war: '**/*.war'
                   }
}
