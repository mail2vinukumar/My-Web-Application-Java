#!/bin/groovy
pipeline { 
    agent {none}

    stages{
        stage('Prepare'){
            steps {
                script {
                    try {
                        notifyBuild('STARTED') 			    			    
                    } 
                    catch (e) {  			    
                        currentBuild.result = "FAILED"
                        throw e
                    } 
                    finally {  			     			    
                        notifyBuild(currentBuild.result)
                    }
 

                    /*
                    try {                    
                        //Send completion notification DL
                        echo 'Sending email notification'                                                                                                   
                        emailext(body: "Prepare Project - Success ${JOB_NAME} - ${BUILD_NUMBER} Build URL - ${BUILD_URL}", subject: 'Build ${JOB_NAME} - ${BUILD_NUMBER} is Success', to: 'vinu.z.kumar@gmail.com') 
                    } catch(Exception err) {                    
                        emailext(body: "Prepare Project - Job Failed ${JOB_NAME} - ${BUILD_NUMBER} Build URL - ${BUILD_URL}", 
                        subject: 'FAILURE ${JOB_NAME} - ${BUILD_NUMBER} is Failed, Error: ${err}', 
                        to: 'vinu.z.kumar@gmail.com') 
                        throw err
                    }
                    */
 
                    
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
