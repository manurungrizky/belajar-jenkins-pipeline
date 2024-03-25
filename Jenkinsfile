pipeline {
    agent any
    
    stages {
        stage('Test Connection') {
            steps {
                script {
                    // Define your remote server IP address
                    def remoteServer = '172.72.72.11'
                    
                    // Define your username credential ID
                    def credentialsId = 'remote-server-11-credentials'
                    
                    // Command to test connectivity (e.g., SSH)
                    def command = "ssh -o BatchMode=yes -o ConnectTimeout=5 ${credentialsId}@${remoteServer} exit"

                    // Execute the command
                    def result = sh(script: command, returnStatus: true)

                    // Check if the command executed successfully
                    if (result == 0) {
                        echo "Connection to ${remoteServer} successful"
                    } else {
                        error "Connection to ${remoteServer} failed"
                    }
                }
            }
        }
    }
}
