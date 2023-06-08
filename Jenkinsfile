pipeline {
    agent {
        label "agent"; 
    }
    environment {
        GOOGLE_CREDENTIALS = credentials('gcp-terraform-json')
    }
    stages {
        stage('Terraform init') {
            steps {
                sh 'terraform init'              
            }
        }

        stage('Terraform validate') {
            steps {
                sh 'terraform validate'
            }
        }

        stage('Terraform plan') {
            steps {
                sh 'terraform plan'
            }
        }

        stage('Terraform apply') {         
            steps {
                sh 'terraform apply --auto-approve'
            }
        }
    }
}
