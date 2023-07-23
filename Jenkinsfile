pipeline{
	agent any
	tools {
 		 maven 'mvn_home'
	}
	stages{
		stage('SCM Checkout'){
			steps{
				git branch: 'main', credentialsId: 'git_cred', url: 'https://github.com/riteshalu/tomcat-demo.git'
			}
		}
          stage('sonar-server'){
           		 steps{
              			echo "Sonar Test"
              }
            }
		stage('mvn-package'){
			steps{
				sh 'mvn clean compile package'
			}
		}
		stage('Tomcat-deployment'){
			steps{
				sshagent(['tomcat-cred1']) {
					sh """
    				scp -o StrictHostKeyChecking=no target/tomcat-demo.war ec2-user@43.205.139.96:/opt/tomcat/webapps/
					ssh ec2-user@43.205.139.96 /opt/tomcat/bin/shutdown.sh
					ssh ec2-user@43.205.139.96 /opt/tomcat/bin/startup.sh
					"""
  				}
			}
		}
	}
}
