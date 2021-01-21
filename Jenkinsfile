pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
        }
    }
    

    stages {
        stage('Build') {
            steps {
                sh 'mvn install'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deliver') { 
            steps {
                sh 'pwd;ls -al /var/jenkins_home/workspace/spring/target'                
                sh 'echo "Use addition project to complete this setp zzz"'
            }
        }
    }
}
