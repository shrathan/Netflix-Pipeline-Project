pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                git url: 'https://github.com/shrathan/Netflix-Pipeline-Project.git'
            }
        }
        
        stage('Package the code') {
            steps {
                script {
                    def mavenHome = tool name:"maven s/w", type:"maven"
                    def mavenCMD = "${mavenHome}/bin/mvn"
                    sh "${mavenCMD} clean package"
                }
            }
        }
        stage('Build the code') {
            steps {
                script {
                    sh "sudo cp target/NETFLIX-1.2.2.war /root/apache-tomcat-9.0.90/webapps"
                }
            }
        }
    }
}
