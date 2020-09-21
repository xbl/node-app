pipeline {
    agent any

    parameters {
        string(name: 'Tag', defaultValue: '1.0', description: 'Please input git tag!')
    }

    stages {
        stage('echo') {
            steps {
                echo "Git is ${params.Tag}"
            }
        }

        stage('Deploy') {
            steps {
                sh 'ansible-playbook -i /home/workspace/inventory/hosts deploy-app.yml'
            }
        }
    }
}