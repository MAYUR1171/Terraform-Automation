pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
checkout scmGit(branches: [[name: '*/maine']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/MAYUR1171/Terraform-Automation.git']])            }
        }
    
        stage ("terraform init") {
            steps {
                sh ("terraform init -reconfigure") 
            }
        }
        
        stage ("plan") {
            steps {
                sh ('terraform plan') 
            }
        }

        stage (" Action") {
            steps {
                echo "Terraform action is --> ${action}"
                sh ('terraform ${action} --auto-approve') 
           }
        }
    }
}
