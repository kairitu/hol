pipeline {
    agent any
    tools {
        maven 'M2_HOME'
    }

    stages {
        
        stage('Build') {
            steps {
                echo 'Hello Build'
                sh 'mvn clean'
                sh 'mvn install'
                sh 'mvn package'
            }
        }
        
        stage('Test') {
            steps {
                sh 'mvn test;
            }
        }
        
        stage('Build and publish image') {
            steps {
                script {
                 checkout scm
                    docker.withRegistry('', 'DockerRegID') {
                        def customimage = docker.build("kairitu16/hol-pipeline:${env.BUILD_ID}")
                        customimage.push()
                    }
                }
               
            }
        }
    }
}

