pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                echo 'Code cloned successfully'
            }
        }

        stage('Build') {
            steps {
                echo 'Building HTML project...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing project...'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                scp -i /home/ubuntu/jenkins-key.pem -o StrictHostKeyChecking=no index1.html ubuntu@16.170.203.189:/tmp/
                ssh -i /home/ubuntu/jenkins-key.pem ubuntu@16.170.203.189 "sudo mv /tmp/index1.html /var/www/html/index.html"
                '''
            }
        }

    }
}
