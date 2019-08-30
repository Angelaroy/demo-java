pipeline {
    agent any
    tools {
        maven 'maven-3.5.4'
        jdk 'Java'
    }
    stages {
        stage('git clone') {
            steps {
                git credentialsId: 'git-pwd', url: 'https://github.com/Angelaroy/demo-java.git'
                echo "Successful"
            }
        }
        stage ('Maven Build') {
            steps {
                bat label: '', script: 'mvn -Dmaven.test.failure.ignore=true install'
                echo "War file created successfully"
            }
        }
        stage('Build dockerfile') {
            steps {
                echo "Starting to build docker image"
                script {
                        checkout scm
                        def customImage = docker.build("test-image", "Dockerfile")
                        customImage.push()
                }
            }
        }
    }
}
