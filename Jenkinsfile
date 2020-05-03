pipeline {
    agent any

    stages {
        stage('Build') {
            agent { label 'slave' }
            steps {
                echo 'Building..'
                sh '''
                   pwd
                   ansible node -m ping
                   ansible-playbook deploy.yaml
                '''
            }
        }
    }    
}
