pipeline {  
    agent any
    tools {
       maven 'Maven'
       jdk 'JAVA'
        
        stages {  
            stage ('Git-Checkout') {  
                steps{
                    git credentialsId: 'Santhosh-Nagarajan/******(git credential)', url: 'https://github.com/Santhosh-Nagarajan/hello-word-webapp.git'
                    echo "Checkout successful";
                } 
            }
            stage ('Compile') {  
                  steps{
                    sh label: '', script: 'mvn compile'
                    echo "test successful";
                    
                } 
            }
            stage ('Build') {  
                  steps{
                    sh 'mvn clean'
                    sh 'mvn package'
                    echo "build successful";
                    
                } 
            }
             stage ('Test') {  
                  steps{
                    sh 'mvn test'
                    echo "test successful";
                } 
            }
            
        stage ('Deploy') {
            steps{
            deploy adapters: [tomcat9(path: '', url: 'http://localhost:8082/')], contextPath: '/pipeline', onFailure: false, war: 'webapp/target/*.war' 
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
