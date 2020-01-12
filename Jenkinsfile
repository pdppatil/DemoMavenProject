pipeline {
    agent any 
    stages {
        stage('Package') { 
            steps {
                bat "mvn package"
            }
        }
        stage('Build_Image') { 
            steps {
                bat "docker build -t pdppatil/webapp:1.0 ."
            }
        }   
        stage('Push_Image') { 
            steps {
                withCredentials([string(credentialsId: 'docker-pwd', variable: 'dockerHubPwd')]) {
                    bat "docker login -u pdppatil -p ${dockerHubPwd}"
    
}
                
                bat "docker push pdppatil/webapp:1.0"
            }
        }
        
        stage('Run_Image') { 
            steps {
                bat "docker run -p 8080:8080 -d --name myapp pdppatil/webapp:1.0"
            }
        } 
    }
}

