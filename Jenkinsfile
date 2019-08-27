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
                sh 'rm -r *;git clone https://github.com/icpaws/icpawscfn2.git'
            }
        }
        stage('terraform init') {
            steps {
                sh 'terraform init /var/jenkins_home/workspace/AWS/build_icpawsterraformdem/icpawscfn2'
            }
        }
        stage('terraform plan') {
            steps {               
                sh 'ls /var/jenkins_home/workspace/AWS/build_icpawsterraformdemo/icpawscfn2; terraform plan /var/jenkins_home/workspace/AWS/build_icpawsterraformdemo/icpawscfn2'
            }
        }
        stage('terraform apply') {
            steps {
                sh 'echo "Ended....!!"'
                sh 'terraform apply -auto-approve /var/jenkins_home/workspace/AWS/build_icpawsterraformdemo/icpawscfn2'
            }
        }

        
    }
}
