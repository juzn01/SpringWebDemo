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
                sh 'cp spingwebdemo.war tomcat:/usr/local/tomcat/webapps/'
                sh 'curl -I tomcat:8080/springwebdemo/'
            }
        }
    }
}
