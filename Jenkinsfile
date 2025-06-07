pipeline {
  agent any

  environment {
    AWS_DEFAULT_REGION = 'eu-west-1'
    S3_BUCKET = 'pricing-cards'
  }

  stages {
    stage('Deploy to S3') {
      steps {
        withCredentials([
          string(credentialsId: 'aws-access-key-id-lsp', variable: 'AWS_ACCESS_KEY_ID'),
          string(credentialsId: 'aws-secret-access-key-lsp', variable: 'AWS_SECRET_ACCESS_KEY')
        ]) {
          sh '''
            echo "Deploying to S3..."
            aws s3 sync . s3://$S3_BUCKET \
              --delete \
              --exclude ".git/*" \
              --exclude "Jenkinsfile" \
              --exclude "*.md"
          '''
        }
      }
    }
  }
}
