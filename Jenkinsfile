pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                sh 'ansible-playbook -i /home/workspace/inventory/hosts deploy-app.yml'
            }
        }
    }
}