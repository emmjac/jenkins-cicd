pipeline {
    agent any
    environment {
       // AWS_REGION = 'us-east-1'
        MAVEN_HOME = '/usr/share/maven'  // maven home directory. 
    }
    stages {
        stage('Checkout Code') {
            steps {
               // replace git URL below with your git repo url
                git branch: 'main', url: 'https://github.com/mecbob/jenkins-cicd.git'
            }
        }

        stage('Build with Maven') {
            steps {
                sh "${MAVEN_HOME}/bin/mvn clean compile test package"
            }
        }




        // stage('Initialize Terraform') {
        //     steps {
        //         sh 'terraform init'
        //     }
        // }
        // stage('Plan Terraform') {
        //     steps {
        //         sh 'terraform plan -out=tfplan'
        //     }
        // }
        // stage('Apply Terraform') {
        //     steps {
        //         input message: "Approve deployment?", ok: "Deploy"
        //         sh 'terraform apply tfplan'
        //     }
        // }
    }
}