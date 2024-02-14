pipeline {
    agent any
    
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/spring-petclinic/spring-petclinic-microservices.git'
            }
        }
        
        stage('Build') {
            steps {
                sh 'mvn install'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                echo "docker build"
               // sh 'docker build -t my-custom-image .'
               // sh 'docker tag my-custom-image <your-docker-registry>/<image-name>:<tag>'
               // sh 'docker push <your-docker-registry>/<image-name>:<tag>'
            }
        }
        
        stage('Send Artifact to Nexus') {
            steps {
                echo "nexus"
                // Implement the logic to send the artifact to Nexus repository
                // You may need to use a Nexus plugin or Maven deploy plugin
            }
        }
        
        stage('Deploy') {
            steps {
              echo "deploy"
              //  sh 'java -jar /path/to/your/artifact/application.jar'
            }
        }
    }
}
