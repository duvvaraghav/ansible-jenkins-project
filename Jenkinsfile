pipeline {
    agent any

    stages {
        stage('Build') {
            agent { label 'slave' }
            steps {
                echo 'Building..'
                sh '''
                   cd /home/ubuntu/playbook
                   pwd
                   ansible node -m ping
                '''
            }
        }
    }    
}
