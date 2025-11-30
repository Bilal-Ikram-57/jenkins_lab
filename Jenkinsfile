pipeline {
    agent any

    parameters {
        // 1. String parameter
        string(
            name: 'VERSION',
            defaultValue: '1.0.0',
            description: 'Version to deploy on prod'
        )

        // 2. Dropdown / choice parameter
        choice(
            name: 'RELEASE_VERSION',
            choices: ['1.1.0', '1.2.0', '1.3.0'],
            description: 'Select Release Version'
        )

        // 3. Boolean parameter to enable/disable Test stage
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
                echo "Deploy version: ${VERSION}"
                echo "Release selected: ${RELEASE_VERSION}"
                echo "Build version value from env var: ${NEW_VERSION}"
            }
        }

        stage('Test') {
            when {
                expression { params.executeTests }   // 🔥 Runs only if checkbox = true
            }
            steps {
                echo "Running test cases..."
                echo "Tests executed successfully!"
            }
        }
    }
}
