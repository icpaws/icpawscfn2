pipeline {
    agent {
        node {
            label 'master'
        }
    }

    stages {

        stage('terraform started') {
            steps {
                sh 'echo "Started...!" '
            }
        }
        stage('git clone') {
            steps {
                sh 'rm -r *;sudo git clone https://github.com/icpaws/icpawscfn.git'
            }
        }
        stage('terraform init') {
            steps {
                sh 'terraform init /var/jenkins_home/workspace/AWS/icpawsterraformdemo/icpawscfn'
            }
        }
        stage('terraform plan') {
            steps {
                sh 'ls /var/jenkins_home/workspace/AWS/icpawsterraformdemo/icpawscfn; terraform plan /var/jenkins_home/workspace/AWS/icpawsterraformdemo/icpawscfn'
            }
        }
        stage('terraform apply') {
            steps {
                sh 'echo "Ended....!!"'
                sh 'terraform apply -auto-approve'
            }
        }

        
    }
}
