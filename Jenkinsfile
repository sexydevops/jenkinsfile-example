def example_string = 'test'
pipeline {
    agent any
    parameters {
      string(name: 'ENV', defaultValue: params.ENV ?:'dev', description: 'What is your environment, e.g. dev, stg?')
      string(name: 'HOST', defaultValue: params.HOST ?:'localhost', description: 'What is your host name?')
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh "ls"
                sh """
                cat << EOF > .env
ENV=$ENV
HOST=$HOST
EOF
                """
                sh "cat .env"
            }
        }
        stage('Test') {
            steps {
                sh "ls"
                echo "Testing.."
                sh "cat .env"
            }
        }
    }
}
