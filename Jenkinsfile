pipeline {
    agent any

    environment {
        REMOTE_HOST = "172.72.72.21"
        REMOTE_USER = "wmuser"
        REMOTE_PATH = "/home/wmuser/sag"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git credentialsId: 'github-manurungrizky', url: 'git@github.com:manurungrizky/belajar-jenkins-pipeline.git'

                sshagent(['ssh-credential-21']) {
                    sh """
                        ssh ${REMOTE_USER}@${REMOTE_HOST} "rm -rf ${REMOTE_PATH}/*"
                        scp -r * ${REMOTE_USER}@${REMOTE_HOST}:${REMOTE_PATH}
                    """
                }
            }
        }
    }
}
