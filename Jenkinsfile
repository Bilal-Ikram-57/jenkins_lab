flag = true

pipeline {
    agent any

    stages {

        stage('build') {
            steps {
                echo 'Building Project'
            }
        }

        stage('test') {
            when {
                expression {
                    // condition — similar to your screenshot
                    flag == true
                }
            }
            steps {
                echo 'Running Test Stage'
                // change flag like in your screenshot
                flag = false
            }
        }

        stage('deploy') {
            steps {
                echo 'Deploying Project'
            }
        }
    }

    post {

        always {
            echo 'Post build condition running'
        }

        failure {
            echo 'Post Action if Build Failed'
        }
    }
}
