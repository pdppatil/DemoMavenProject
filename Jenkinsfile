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
                bat "docker build -t="pdppatil/webapp:1.0" . "
            }
        }
        
        
    }
}

