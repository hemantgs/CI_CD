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
            steps{
              bat 'mvn clean install'
            }
      }
   }
}