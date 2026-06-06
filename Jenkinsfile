pipeline {
    agent any

    environment {
        ARM_CLIENT_ID       = credentials('ARM_CLIENT_ID')
        ARM_CLIENT_SECRET   = credentials('ARM_CLIENT_SECRET')
        ARM_SUBSCRIPTION_ID = credentials('ARM_SUBSCRIPTION_ID')
        ARM_TENANT_ID       = credentials('ARM_TENANT_ID')
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Terraform Init') {
            steps {
                bat '"C:\\terraform\\terraform.exe" init'
            }
        }

        stage('Terraform Validate') {
            steps {
                bat '"C:\\terraform\\terraform.exe" validate'
            }
        }

        stage('Terraform Plan') {
            steps {
                bat '"C:\\terraform\\terraform.exe" plan'
            }
        }

        stage('Terraform Apply') {
            steps {
                bat '"C:\\terraform\\terraform.exe" apply -auto-approve'
            }
        }
    }
}
