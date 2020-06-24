pipeline {
    agent any
    stages {
        stage('---clean---') {
            steps {
                sh "mvn clean"
            }
        }
        stage('--compile--') {
            steps {
                sh "mvn compile"
            }
        }
        stage('--test--') {
            steps {
                sh "mvn test"
            }
        }
        stage('--package--') {
            steps {
                sh "mvn package"
            }
        }
        stage('deploy') {
            steps {
                sh "scp /root/.jenkins/workspace/pipeline2/target/my-app-1.0-SNAPSHOT.jar 35.222.19.25:/opt/apache-tomcat-9.0.36/webapps"
                sh "echo file deployed!"
            }
        }
    }
}
