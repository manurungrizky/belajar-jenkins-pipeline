pipeline {
    agent any

    environment {
        REMOTE_SERVER_CREDENTIALS = credentials('remote-server-11-credentials')
    }

    stages {
        stage('Test Remote Server Credentials') {
            steps {
                sshagent([env.REMOTE_SERVER_CREDENTIALS]) {
                    sh 'ssh wmuser@172.72.72.11 "echo Remote server credentials are working"'
                }
            }
        }
    }
}
