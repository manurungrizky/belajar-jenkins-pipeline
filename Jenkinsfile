pipeline {
    agent any

    environment {
        GIT_CREDENTIALS = credentials('github-manurungrizky')
        REMOTE_SERVER_CREDENTIALS = credentials('remote-server-11-credentials')
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main',
                    url: 'git@github.com:manurungrizky/belajar-jenkins-pipeline.git',
                    credentialsId: env.GIT_CREDENTIALS
            }
        }

        stage('Test Remote Server Credentials') {
            steps {
                sshagent([env.REMOTE_SERVER_CREDENTIALS]) {
                    sh 'ssh wmuser@172.72.72.11 "echo Remote server credentials are working"'
                }
            }
        }

        stage('Copy to Remote Server') {
            steps {
                sshagent([env.REMOTE_SERVER_CREDENTIALS]) {
                    sh '''
                        ssh wmuser@172.72.72.11 "rm -rf /home/wmuser/sag/*"
                        scp -r * wmuser@172.72.72.11:/home/wmuser/sag
                    '''
                }
            }
        }
    }
}
