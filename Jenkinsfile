pipeline {
    agent any

    parameters {
        string(
            name: 'VERSION',
            defaultValue: '1.0.0',
            description: 'Version to deploy on prod'
        )

        choice(
            name: 'RELEASE_VERSION',
            choices: ['1.1.0', '1.2.0', '1.3.0'],
            description: 'Select Release Version'
        )

        booleanParam(
            name: 'executeTests',
            defaultValue: true,
            description: 'Enable Test Stage?'
        )
    }

    environment {
        NEW_VERSION = '1.3.0'
    }

    stages {

        stage('Build') {
            steps {
                echo "Building Project..."
                echo "Deploy version: ${params.VERSION}"
                echo "Release selected: ${params.RELEASE_VERSION}"
                echo "Env variable value: ${env.NEW_VERSION}"
            }
        }

        stage('Test') {
            when { expression { params.executeTests } }
            steps {
                echo "Running tests..."
                echo "Test stage executed!"
            }
        }
    }
}
