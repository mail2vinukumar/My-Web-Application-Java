pipeline { 
    agent none
    stages{
        stage('Prepare'){
            steps {
                node {
                    stage "Create build output"
                echo 'Hello, JDK'
                    
                    stage "Create build output2"
                sh 'ls -l'
                sh 'date'
                }
            }
        }
        stage('Build'){
            steps {
                echo 'Hello, JDK'
            }            
        }
        stage('Test'){
            steps {
                echo 'Hello, JDK'
            }            
        }
        stage('Deploy'){
            steps {
                echo 'Hello, JDK'
            }            
        }        
    }
}
