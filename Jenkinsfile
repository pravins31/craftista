pipeline{
    agent any
    tools{
        maven '3.9.7'
        
    }
    stages{
        stage('voting build'){
            steps{
                echo 'compling voting app'
                
                dir('voting'){
                    
                    sh 'mvn compile'
                    
                }
            }
            
        }
        stage('voting Test'){
            steps{
                echo 'compling voting app'
                
                dir('voting'){
                    
                    sh 'mvn test'
                    
                }
            }
            
        }
        stage('voting package'){
            steps{
                echo 'compling voting app'
                
                dir('voting'){
                    
                    sh 'mvn package -DskipTests'
                    
                }
            }
            
        }
    }
}
