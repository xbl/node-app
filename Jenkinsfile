pipeline {
    agent any

    options {
        timestamps()
    }

    parameters {
        string(name: 'Tag', defaultValue: 'v1.0', description: 'Please input git tag!')
    }

    stages {
        stage('Git Clone') {
            steps {
                git url: 'https://github.com/xbl/node-app.git', branch: 'master'
            }
        }
        stage('Checkout Tag') {
            steps {
                echo "Git is ${params.Tag}"
                sh "git checkout tags/${params.Tag} -b latest"
            }
        }

        stage('Deploy') {
            steps {
                sh 'ansible-playbook -i /home/workspace/inventory/hosts deploy-app.yml'
            }
        }
    }
}