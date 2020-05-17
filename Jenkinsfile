pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                withAWS(credentials:'aws-static', region:'us-west-2') {
                    sh 'env'
                    sh 'aws sts get-caller-identity'
                    s3Upload(file:'index.html', bucket:'uiruninja-static', path:'index.html')
                }
            }
        }
    }
}