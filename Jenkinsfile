pipeline
{
agent any
stages
{
stage ('git clone')
{
steps
{git 'https://github.com/saurabhsingh1717/maven-project'
}
}
stage ('compile my project')
{
steps
{
withMaven(jdk: 'LocalJDK', maven:'LocalMaven')
{
sh 'mvn compile'
}
}
}
stage ('test my project')
{
steps
{
withMaven(jdk: 'LocalJDK', maven:'LocalMaven')
{
sh 'mvn test'
}
}
}
stage ('build my project')
{
steps
{
withMaven(jdk: 'LocalJDK', maven:'LocalMaven')
{
sh 'mvn package'
}
}
}
stage ('deploy my project on tomcat')
{
steps
{
sshagent(['tomcat_ssh']) {
sh 'scp -o StrictHostKeyChecking=no */target/*.war ec2-user@172.31.39.172:/var/lib/tomcat/webapps'
}
}
}
}
}
