pipeline {
    agent any
    
    tools {
        maven 'Maven'      // this must match the Maven name configured in Jenkins → Global Tool Configuration
    }

    environment {
        // Environment variable accessible across all stages
        NEW_VERSION = "1.3.0"
    }

    stages {
        stage('Build') {
            steps {
                echo "Building Project..."

                // Print environment variable
                echo "Building version is: ${NEW_VERSION}"

                // Run Maven build
                sh "mvn install"      // executes mvn install command
            }
        }
    }
}
