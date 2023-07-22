pipeline{
	agent any
	tools {
 		 maven 'mvn_home'
	}
	stages{
		stage('SCM Checkout'){
			steps{
				echo "SCM Checkout"
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
