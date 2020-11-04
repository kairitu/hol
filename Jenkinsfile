pipeline {
    agent any
    tools {
        'M2_HOME'
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                sleep 3
            }
        }
       
        stage('Build') {
            steps {
                echo 'Hello Build'
                sh 'mvc clean'
                sh 'mvc install'
                sh 'mvc package'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Hello Deploy'
                sleep 3
            }
        }
        
        stage('Test') {
            steps {
                echo 'Hello Test'
                sleep 3
            }
        }
    }
}

