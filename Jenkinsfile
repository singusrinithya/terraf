pipeline {
  agent any

  environment {
    AWS_ACCESS_KEY_ID = 'AKIAXZ7UM2UFOT5HIVNA'
    AWS_SECRET_ACCESS_KEY = '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'
    AWS_DEFAULT_REGION = 'us-east-1d'
  }

  stages {
    stage('git') {
        steps {
            sh "git pull https://github.com/singusrinithya/terraf.git"
        }
    }
    stage('Terraform Init') {
      steps {
        sh 'terraform init'
      }
    }

    stage('Terraform Plan') {
      steps {
        sh 'terraform plan -out=tfplan'
      }
    }

    stage('Terraform Apply') {
      steps {
        sh 'terraform apply tfplan'
      }
    }
  }
}
