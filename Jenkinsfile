pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                sh 'ansible-playbook -i ./inventory/hosts deploy-app.yml'
            }
        }
    }
}