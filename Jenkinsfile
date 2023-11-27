pipeline {
    agent {
        label 'Node2'
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                deploy adapters: [tomcat7(credentialsId: 'a14976be-c460-43e1-950d-222ad6c7898d', path: '', 
                url: 'http://3.89.58.87:8080/')], contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
