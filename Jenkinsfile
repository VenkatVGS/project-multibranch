pipeline {
    agent any
    stages {
        stage ('Build') {
            steps {
                script{
                     def mvnHome =  tool name: 'maven3', type: 'maven'   
                    sh "${mvnHome}/bin/mvn clean package"
	                sh 'mv target/myweb*.war target/newapp.war'
                }
            }
        }
        stage('Docker Build Images') {
            steps {
                script {
                    sh 'docker build -t naresh2603/multi:v1 .'
                    sh 'docker images'
                }
            }
        }
    }
}
