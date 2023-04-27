#!/usr/bin/env groovy

pipeline {
    agent none
    stages {
        stage('build') {
            steps {
                script {
                    echo "Building the application..."
                }
            }
        }
        stage('test') {
            steps {
                script {
                    echo "Testing the application..."
                }
            }
        }
        stage('deploy') {
            steps {
                script {
                    def dockerCmd = 'docker run -p 3080:3080 -d emmanuelkamto/demo-app:1.1.1-44'
                    sshagent(['ec2-server-key']) {
                    ssh "ssh -o StrickHostKeyChecking=no ec2-user@34.229.72.147 ${dockerCmd}"
                   }
                }
            }
        }
    }
}
