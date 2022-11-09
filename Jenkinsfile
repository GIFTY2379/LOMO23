pipeline {
    agent any
    tools {
        maven "Admin"
    }
    stages {
        stage('Checkout') {
            steps {
                // Get some code from a GitHub repository
                git url: 'https://github.com/Gifty147/LOMO23.git', 
                    branch: 'LOMO23',
                    credentialsId: '97ba5c35-497e-45c0-884e-635bdb4afb60'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test'){
            steps {
                 sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        } 
   }   
}