pipeline {
    agent any

    stages {
        stage('Test Remote Server Credentials') {
            steps {
                script {
                    sshagent(['ssh-credential-21']) {
						sh 'ssh wmuser@172.72.72.21 "echo Remote server credentials are working"'
					}
                }
            }
        }
    }
}
