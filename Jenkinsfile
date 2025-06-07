pipeline {
  agent any

  environment {
    AWS_DEFAULT_REGION = 'eu-west-1'
    S3_BUCKET = 'pricing-cards'
  }

  stages {
    stage('Checkout') {
      steps {
        // git 'https://github.com/ChrisMuteb/pricing-cards.git'
        echo 'Checkout stage completed successfully!'
      }
    }

    stage('Deploy to S3') {
      steps {
        sh 'aws s3 sync . s3://$S3_BUCKET --delete --exclude ".git/*"'
      }
    }
  }
}
