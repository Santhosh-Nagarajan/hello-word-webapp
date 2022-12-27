/* pipeline {  
    agent any
    tools {
       maven 'Maven'
    }
        
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
            deploy adapters: [tomcat9(credentialsId: 'creds', path: '', url: 'http://localhost:9090/')], contextPath: 'java-maven-pipeline-tomcat', war: '**/*.war'
             echo "Deploy successful";
            }
        }
        stage ('Monitor') { 
           steps{ 
             echo "Now you can monitor!";
           }
        }
     }
   } */
    
    pipeline {  
    agent any
    tools {
       maven 'Maven'
    }
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
            deploy adapters: [tomcat9(credentialsId: 'creds', path: '', url: 'http://localhost:9090/')], contextPath: 'java-maven-pipeline-tomcat',war: '**/*.war' 
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
