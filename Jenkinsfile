pipeline {
    agent any

    stages {
        stage('SCM') {
            steps {    git 'https://github.com/awspandian/azcs.git'       
            }
        }
		stage('Build') {
            steps {   
				sh label: '', script: 'mvn clean'
				sh label: '', script: 'mvn install'
            }
        }
        stage('Deployment') {
            steps {    sh label: '', script: 'cp -rp "/var/lib/jenkins/workspace/sample-pipeline/target/azcs.war" "/opt/apache-tomcat/webapps"'
            }
        }
    }
}
