node{
stage('git checkout'){
  git 'https://github.com/practicedevops11/Jenkins'
}
stage('package building'){
  //giving maven home path
  def mvnhome = tool name: 'maven-3', type: 'maven'
  //as we are defining a varible sh should be double quotes and anything you want to run on terminal you can use sh 
  // and here you have to run mvn clean pacakge in workspace to generte war file for that you have to use sh
  sh "${mvnhome}/bin/mvn clean package" 

}
  
  stage('tomcat deploy')
  {
    
    sshagent(['tomcat-demo']) {
    sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/jenkinsfile-git and maven/target/myweb-0.0.7-SNAPSHOT.war centos@172.31.34.197:/opt/apache-tomcat-8.5.46/webapps'
}
  }
  
  stage('slack notification')
  {
    slackSend baseUrl: 'https://hooks.slack.com/services/', 
      channel: 'devops', 
      color: 'good',
      message: 'welcome to jenkins monitoring',
      tokenCredentialId: 'slack-demo'
  }
}
