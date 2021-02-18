def string = 'test'
pipeline {
    agent any
    parameters {
      string(name: 'ENV', defaultValue: params.ENV ?:'dev', description: 'What is your environment, e.g. dev, stg?')
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
