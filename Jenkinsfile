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
}
