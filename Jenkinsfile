node('nodes')
{
properties([[$class: 'JiraProjectProperty'], buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])
def mavenhome = tool name: "maven3.6.3"
stage("checkout code")
{
git branch: 'development', credentialsId: 'f2f6adb8-2a3f-49a3-b8f5-a69c47efe704', url: 'https://github.com/karthikdevopstraining/maven-web-application.git'
}
stage("build")
{
sh "${mavenhome}/bin/mvn clean package"
}
/*
stage("sonarqube report")
{
sh "${mavenhome}/bin/mvn sonar:sonar"
}
stage("nexus")
{
sh "${mavenhome}/bin/mvn deploy"
}
stage("tomcat")
{
sshagent(['dc5fabdd-ea9e-489a-bb58-42468946d41a']) 
{
   sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@52.66.195.86:/opt/apache-tomcat-9.0.31/webapps/"
}
}
stage("email")
{
emailext body: 'build is over', subject: 'build is over', to: 'karthik.klb@gmail.com'
}
*/
}
