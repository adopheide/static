pipeline {
    agent any
    stages {
        stage('Upload to AWS.') {
            steps {
                sh 'echo "Connecting to AWS Region"'
                    withAWS(region:'us-east-2') {
                        // do something
                    }
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
}