pipeline {
    agent any
    stages {
        stage('Lint HTML.') {
            steps {
                sh '''
                    echo "Linting"
                    tidy -q -e *.html
                '''
            }
        }
        stage('Upload to AWS.') {
            steps {
                sh 'echo "Connecting to AWS"'
                withAWS(region: 'us-east-2', credentials: 'myaccess') {
                    sh 'echo "index.html">index.html'
                    s3Upload(file:'/var/lib/jenkins/workspace/static_master/index.html', bucket:'dopheide-jenkins-s3', path:'', acl:'PublicRead')
                }
                sh 'echo "Upload complete"'
            }
        }
    }
}