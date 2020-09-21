pipeline {
    agent any

    parameters {
        string(name: 'Tag', defaultValue: 'v1.0', description: 'Please input git tag!')
    }

    stages {
        stage('Checkout Tag') {
            steps {
                echo "Git is ${params.Tag}"
                sh "git checkout tags/${params.Tag} -b latest"
            }
        }

        stage('Deploy') {
            steps {
                sh 'ansible-playbook -i /home/workspace/inventory/hosts deploy-app.yml'
                deleteDir()
            }
        }
    }
}