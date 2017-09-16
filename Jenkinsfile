//pipeline {
//    stages {
//        
//        stage('Build binaries'){
//            checkout scm
//        }
//        
//        
//        
//    }
//    
//    
//    
//    
//}

node {
    
   stages {
                    
        stage('Build binaries'){
           checkout scm
              bat 'mvn clean install'
      }
   }
}