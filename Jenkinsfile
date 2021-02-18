def example_string = 'test'
pipeline {
    agent any
    parameters {
      string(name: 'ENV', defaultValue: params.ENV ?:'dev', description: 'What is your environment, e.g. dev, stg?')
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh "ls"
                sh """
                cat << EOF > .env
                S3URL=$S3URL
                DBURL=$DBURL
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
