pipeline {
    agent any

    stages {
        stage('SCM') {
            steps { 
                git 'https://github.com/awspandian/azcs.git'
            }
        }
		stage('BUILD') {
            steps {
					sh 'mvn clean'
					sh 'mvn install'
					
            }
        }
		stage('Deploy') {
            steps {
					sh 'cp -rp "/var/lib/jenkins/workspace/demo-pipe/target/azcs.war" "/opt/apache-tomcat/webapps"'
					
            }
        }
    }
}
