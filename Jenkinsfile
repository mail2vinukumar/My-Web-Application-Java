pipeline { 
    agent none
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
    script{
    	def notifyBuild(String buildStatus = 'STARTED') {
    		// build status of null means successful
  			buildStatus =  buildStatus ?: 'SUCCESSFUL'
 
  			// Default values
  			def colorName = 'RED'
  			def colorCode = '#FF0000'
  			def subject = "${buildStatus}: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'"
  			def summary = "${subject} (${env.BUILD_URL})"
  			def details = """<p>STARTED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':</p>
    			<p>Check console output at "<a href="${env.BUILD_URL}">${env.JOB_NAME} [${env.BUILD_NUMBER}]</a>"</p>"""
 
  			// Override default values based on build status
  			if (buildStatus == 'STARTED') {
  			  color = 'YELLOW'
  			  colorCode = '#FFFF00'
  			} else if (buildStatus == 'SUCCESSFUL') {
  			  color = 'GREEN'
  			  colorCode = '#00FF00'
  			} else {
  			  color = 'RED'
  			  colorCode = '#FF0000'
  			}
 
  			// Send notifications
  			slackSend (color: colorCode, message: summary)
 
  			hipchatSend (color: color, notify: true, message: summary)
 
  			emailext (
     			 subject: subject,
     			 body: details,
      			to: 'vinu.z.kumar@gmail.com'
    		)
  
		}
        
    }    

}
