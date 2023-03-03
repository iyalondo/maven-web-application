pipeline{
  agent  any
  tools  {
    maven "maven"
  }
  stages {
   stage('1getcode'){
    steps{
      sh "echo 'cloning the latest app version' "
      git credentialsId: 'github', url: 'https://github.com/iyalondo/maven-web-application.git'
    }
   }
   stage('2Test&Build'){
    steps{
      sh "mvn clean package"
    }
   }
 /*  
   stage('3codeQuality'){
    steps{
      sh "mvn sonar:sonar"
    }
   }
   stage('4uploadArtifacts'){
    steps{
      sh "mvn deploy"
    }
   }
   stage('5deploy2UAT'){
    steps{deploy adapters: [tomcat9(credentialsId: 'tomcattest', path: '', url: 'http://18.188.217.171:8080/')], contextPath: null, war: 'target/*war'
    }

    }
   }
   /*stage('6approvalGate'){}
   stage('7deploy2Prod'){}
   stage('8emailNotification'){}
  }
  post   {
    always{}
    success{}
    failure{}
    */
  }
}
