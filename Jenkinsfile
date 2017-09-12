pipeline {
	agent any
	stages{
		stage('build'){
			steps{
				bat 'mvn clean install'
			}
		}
		 // start of deploy state
   		 stage('deploy') {
     		 // define step to run
     			 steps {
        	//invoke command to stop tomcat service
       			 	bat 'C:\\Users\\iplou00\Documents\\jenkins-apache-env\\stop_apache.bat'
        			bat 'ping 127.0.0.1 -n 6'
        			// copy war file from build target to webapp Tomcat folder
        			bat 'xcopy /y C:\\Users\\iplou00\\.jenkins\\workspace\\GOL_Pipeline\\gameoflife-web\\target\\gameoflife.war "C:\\apache-tomcat-7.0.79\\webapps"'
        			//invoke command to start tomcat service      
        			bat 'C:\\Users\\iplou00\\Documents\\jenkins-apache-env\\start_apache.bat'
      			}
    		} 
	}
}

