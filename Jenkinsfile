pipeline {
    agent { label 'centos_worker' }
    environment {
        GITLAB_CREDS = credentials('885b22af-cd79-48e1-92eb-a7c36b4420f9')
    }

    stages {
        stage('Sandbox') {
            steps {
                sh '''GIT_SSH_COMMAND="ssh -i '${GITLAB_CREDS}' -v" git clone git@gitlab.cee.redhat.com:service/app-interface.git'''
            }
        }
    }
}
