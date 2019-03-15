pipeline {    
  agent any    
  stages {        
   
    stage('Checkout') {            
      steps {                
        git credentialsId: 'GIT', url: 'https://github.com/smauerer/myRep.git'           
      }        
    }
    stage('MVN build') {            
      steps {                
        sh 'mvn -f devops-cicd-demo-project-master/pom.xml clean install -DskipTests'          
      }        
    }
    stage('MVN test') {            
      steps {                
        sh 'mvn -f devops-cicd-demo-project-master/pom.xml test'          
      }        
    }
  }
}