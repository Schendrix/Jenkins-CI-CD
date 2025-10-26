    pipeline {
    agent { 
        node {
            label 'agent-docker-python'
            }
    }   
    triggers {
        pollSCM '*/5 * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building..."
                sh '''
                pip install fire
                echo "doing build stuff.."
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                python3 fire.py
                echo "doing test stuff.."
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}