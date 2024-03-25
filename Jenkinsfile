pipeline {
    agent any

    environment {
        REMOTE_SERVER_CREDENTIALS = credentials('credential-ssh-11')
    }

    stages {
        stage('Test Remote Server Credentials') {
            steps {
                script {
                    sshagent(credentials: [env.REMOTE_SERVER_CREDENTIALS]) {
                        sh 'ssh wmuser@172.72.72.11 "echo Remote server credentials are working"'
                    }
                }
            }
        }
    }
}
