
pipeline{
    tools{
        jdk 'MyJava'
        maven 'MyMaven'
    }
	agent none
      stages{
           stage('Checkout'){
            agent any
               steps{
		 echo 'cloning..'
                 git 'https://github.com/ukino1/DevOpsCodeDemo.git'
              }
          }
          stage('Compile'){
            agent { label 'jenkins_slave1'}
              steps{
                  echo 'complie the code..'
                  sh 'mvn compile'
	      }
          }
          stage('CodeReview'){
            agent { label 'jenkins_slave1'}
              steps{
		    
		  echo 'codeReview'
                  sh 'mvn pmd:pmd'
              }
          }
           stage('UnitTest'){
            agent { label 'jenkins_slave1'}
              steps{
                echo 'Testing'
                  sh 'mvn test'
              }
          }
          stage('Package'){
            agent any
              steps{
		  
                  sh 'mvn package'
              }
          }
	     
          
      }
}
