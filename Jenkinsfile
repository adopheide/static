pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Connecting to AWS"'
                withAWS(region: 'us-east-2', credentialsId: 'myaccess') {
                    sh 'echo "index.html">index.html'
                    s3Upload(file:'index.html', bucket:'dopheide-jenkins-s3', path:'/test')
                }
            }

        }
    }
}