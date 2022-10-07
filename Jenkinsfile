node('built-in') 
{
    stage('Continuous Downloads') 
	{
    	git 'https://github.com/sunildevops77/maven.git'
	}

    stage('Continuous Build') 
	{
    	sh 'mvn package'
	}

    stage('Continuous Deployment') 
	{
    	sh '''scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.23.42:/var/lib/tomcat9/webapps/qaenv.war'''
	}

    stage('Continuous Testing') 
	{
    	sh 'echo "Testing Passed"'
	}

    stage('Continuous Delivery') 
	{
    	    	sh '''scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.26.55:/var/lib/tomcat9/webapps/prodenv.war'''
	}
}

