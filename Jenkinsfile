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
                sh 'docker cp jenkins:/usr/bin/scp /tmp/; chmod +x /tmp/scp'
                sh '/tmp/scp `pwd`/target/springwebdemo.war tomcat:/usr/local/tomcat/webapps/'
                sh 'curl -I tomcat:8080/springwebdemo/'
            }
        }
    }
}
