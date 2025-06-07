pipeline {
  agent any

//   environment {
//     AWS_DEFAULT_REGION = 'us-east-1'
//     S3_BUCKET = 'my-static-site-bucket'
//   }

  stages {
    stage ('hello') {
        steps {
            echo 'Hello World'
        }
    }
    // stage('Checkout') {
    //   steps {
    //     git 'https://github.com/ChrisMuteb/pricing-cards.git'
    //   }
    // }

    // stage('Deploy to S3') {
    //   steps {
    //     sh 'aws s3 sync . s3://$S3_BUCKET --delete --exclude ".git/*"'
    //   }
    // }
  }
}
