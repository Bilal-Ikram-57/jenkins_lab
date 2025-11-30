pipeline {
    agent any

    environment {
        // Variables defined here can be used by any stage
        NEW_VERSION = '1.3.0'
    }

    stages {

        stage('build') {
            steps {
                echo 'Building Project'
                // Using environment variable
                echo "Building version ${NEW_VERSION}"
            }
        }

        stage('test') {
            steps {
                echo "Testing version ${NEW_VERSION}"
            }
        }

        stage('deploy') {
            steps {
                echo "Deploying version ${NEW_VERSION}"
            }
        }
    }
}
