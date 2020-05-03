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
                   sudo ansible node -m ping
                '''
            }
        }
    }    
}
