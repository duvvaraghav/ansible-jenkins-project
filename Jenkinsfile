pipeline {
    agent any

    stages {
        stage('Build') {
            agent { label 'slave' }
            steps {
                echo 'jenkins_ansible_integrationsetup..'
                sh '''
                '''
            }
        }
        stage('TEST') {
            agent { label 'slave' }
            steps {
                echo 'host checking..'
                sh '''
                   ansible node -m ping
                '''
            }
        }
        stage('DEPLOY') {
            agent { label 'slave' }
            steps {
                echo 'deploying..'
                sh '''
                   ansible-playbook deploy.yaml
                '''
            }
        }       
        post {
            failure {
                script {
                   currentBuild.result = 'FAILURE'
                }
            }

            always {
                step([$class: 'Mailer',
                   notifyEveryUnstableBuild: true,
                   recipients: "duvva.raghavendra@gmail.com",
                   sendToIndividuals: true])
            }     
		}       
    }
}
