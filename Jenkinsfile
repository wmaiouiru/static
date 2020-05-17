pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                withAWS(credentials:'aws-static') {
                    // do something
                    s3Upload(file:'index.html', bucket:'uiruninja-static', path:'index.html')
                }
            }
        }
    }
}