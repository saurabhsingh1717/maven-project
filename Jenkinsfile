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
}
}
