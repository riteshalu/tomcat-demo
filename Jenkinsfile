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
          	stage('Test'){
           		 steps{
              			echo "Test"
            }
          }
		stage('Build'){
			steps{
				echo "Build"
			}
		}
		stage('Deploy'){
			steps{
				echo "Deploy to Tomcat Server"
			}
		}
	}
}
