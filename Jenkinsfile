pipeline {
    
    agent any

    stages {
        stage('Checkout') {
            steps {
               git branch: 'main', url: 'https://github.com/oadya/terraform-aws-eks-cluster.git'
            }
        }
        
        stage('terraform init') {
            steps {
                 sh 'terraform init'
            }
        }
        
        stage('terraform validate') {
            steps {
                sh 'terraform validate'
            }
        }
        
        stage('terraform plan') {
            steps {
                 sh 'terraform plan'
            }
        }
        
        stage('terraform Apply/Destroy') {
            steps {
                 sh 'terraform ${action} --auto-approve'
            }
        }
    }
}
