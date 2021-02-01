pipeline {
    agent { label 'centos_worker' }
    environment {
        GITLAB_CREDS = credentials('885b22af-cd79-48e1-92eb-a7c36b4420f9')
    }

    stages {
        stage('Sandbox') {
            steps {
                sh '''cat > ~/.ssh/id_rsa << EOF
${GITLAB_CREDS}
EOF'''
                sh "chmod 600 ~/.ssh/id_rsa"
                sh "ls -lah ~/.ssh/id_rsa"
                sh "ping -c 1 gitlab.cee.redhat.com"
                sh "git clone git@gitlab.cee.redhat.com:service/app-interface.git"
            }
        }
    }
}
