
pipeline {
    agent none
    stages {
        stage('test') {
            steps {
                script {
                    echo "Testing the application..."
                    echo "executing pipeline for branch $BRANCH_NAME"
                }
            }
        }
        stage('build') {
            steps {
                when {
                    expression {
                        BRANCH_NAME == 'master'
                    }
                }
                script {
                    echo "Building the application..."
                }
            }
        }
        stage('deploy') {
            steps {
                 when {
                    expression {
                        BRANCH_NAME == 'master'
                    }
                }
                script {
                    echo "Deploying the application..."
                }
            }
        }
    }
}
