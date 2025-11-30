pipeline {
    agent any

    tools {
        maven 'Maven'   // Must match the exact name in Global Tool Configuration
    }

    environment {
        NEW_VERSION = "1.3.0"
    }

    stages {
        stage('Build') {
            steps {
                echo "Building Project..."
                echo "Building version is: ${NEW_VERSION}"
                
                // Use bat instead of sh for Windows
                bat "mvn -version"
                bat "mvn install"
            }
        }
    }
}
