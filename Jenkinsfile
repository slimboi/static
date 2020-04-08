pipeline {
     agent any
     stages {
         stage('Upload to AWS') {
             steps {
                 sh 'echo "Hello AWS"'
                 sh '''
                     echo "Here is multiline shell steps"
                     ls -lah
                 '''
                  withAWS(region:'eu-west-2',credentials:'aws-static') {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'demo-jenkins-15')
             }
         }
     }
}
