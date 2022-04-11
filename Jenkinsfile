pipeline {
     agent any
     stages {
         stage('Build') {
             steps {
                 sh 'echo "Hello World"'
                 sh '''
                     echo "Multiline shell steps works too"
                     ls -lah
                 '''
             }
         }      
         stage('Upload to AWS') {
              steps {
                  withAWS(region:'ap-southeast-1',credentials:'wach-jenkins-cred') {
                  sh 'echo "Uploading content with AWS creds"'
                    
                        s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'app.py', bucket:'my-tf-test-bucccket41432888999999999')
                      
                  }
              }
         }
     }
}
