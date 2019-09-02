pipeline {
    agent any
    stages {
        stage('Upload to AWS now') {
            steps {
                sh 'echo "Connecting to AWS now"'
                withAWS(region: 'us-east-2', credentials: 'myaccess') {
                    sh 'echo "index.html">index.html'
                    s3Upload(file:'/var/lib/jenkins/workspace/static_master', bucket:'dopheide-jenkins-s3', path:'')
                }
            }

        }
    }
}