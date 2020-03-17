pipeline {
    agent any

    stages {
        stage('install') {
            steps {
	                
              sh  'sudo curl -o kubectl https://amazon-eks.s3-us-west-2.amazonaws.com/1.14.6/2019-08-22/bin/linux/amd64/kubectl'
	         	  sh  'sudo curl -o kubectl.sha256 https://amazon-eks.s3-us-west-2.amazonaws.com/1.14.6/2019-08-22/bin/linux/amd64/kubectl.sha256'
              sh  'sudo openssl sha1 -sha256 kubectl'
              sh  'sudo chmod +x ./kubectl'
              sh  'sudo cp ./kubectl /usr/bin/kubectl && export PATH=$PATH:/usr/bin'
              sh  'echo "export PATH=$PATH:/usr/bin" >> ~/.bashrc'
	      sh  'echo "export PATH=$PATH:/usr/bin" >> ~/.bash_profile'
	      sh  'source ~/.bashrc'
	      sh  'source ~/.bash_profile'
              sh  'sudo kubectl version --short --client'
              sh  'sudo rm -rf ~/.kube && sudo mkdir ~/.kube'                                 
              sh  'sudo touch ~/.kube/config-eks'
              echo 'kubectl done'
              sh  'sudo curl -o aws-iam-authenticator https://amazon-eks.s3-us-west-2.amazonaws.com/1.14.6/2019-08-22/bin/linux/amd64/aws-iam-authenticator'
	      sh  'sudo chmod +x ./aws-iam-authenticator'
	      sh  'sudo cp ./aws-iam-authenticator /usr/bin/aws-iam-authenticator && export PATH=$PATH:/usr/bin'
	      echo 'iam done'
	      sh 'aws-iam-authenticator version'
	     
            }
        }
        
    }
}
