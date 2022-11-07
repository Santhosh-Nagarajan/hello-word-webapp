pipeline {  
    agent any
    tools {
       maven 'maven'
       jdk 'JDK'
        
        stages {  
            stage ('Git-Checkout') {  
                steps{
                    git credentialsId: 'Santhosh-Nagarajan/******(git credential)', url: 'https://github.com/Santhosh-Nagarajan/hello-word-webapp.git'
                    echo "Checkout successful";
                } 
            }
            stage ('Compile') {  
                  steps{
                    bat label: '', script: 'mvn compile'
                    echo "test successful";
                    
                } 
            }
            stage ('Build') {  
                  steps{
                    bat 'mvn clean'
                    bat 'mvn package'
                    echo "build successful";
                    
                } 
            }
             stage ('Test') {  
                  steps{
                    bat 'mvn test'
                    echo "test successful";
                } 
            }
            
        stage ('Deploy') {
            steps{
            deploy adapters: [tomcat9(path: '', url: 'http://localhost:8090/')], contextPath: '/pipeline', onFailure: false, war: 'webapp/target/*.war' 
             echo "Deploy successful";
            }
        }
        stage ('Monitor') { 
           steps{ 
             echo "Now you can monitor!";
           }
        }
     }
   }
}
