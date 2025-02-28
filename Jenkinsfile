pipeline {
    agent any
    stages {
        stage('List S3 Buckets') {
            steps {
                script {
                    withCredentials([aws(accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'aws-jenkins-integration', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY')]) {
                        sh 'aws s3 ls'
                    }
                }
            }
        }
        stage('List VPCs') {
            steps {
                script {
                    withCredentials([aws(accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'aws-jenkins-integration', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY')]) {
                        sh 'aws ec2 describe-vpcs'
                    }
                }
            }
        }
    }
}
