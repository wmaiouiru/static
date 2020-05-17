pipeline {
    agent any
    stages {
        stage('Lint HTML') {
            step {
                sh "tidy -q -e *.html"
            }
        }
        stage('Upload to AWS') {
            steps {
                withAWS(credentials:'aws-static', region:'us-west-2') {
                    s3Upload(file:'./index.html', bucket:'uiruninja-static', path:'index.html')
                }
            }
        }
    }
}