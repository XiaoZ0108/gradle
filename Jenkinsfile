pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/XiaoZ0108/gradle.git'
            }
        }
        stage('Build') {
            steps {

                        sh '.gradlew clean build'
                
            }
        }
        stage('Test') {
            steps {
                
                        sh '.gradlew test'
                  
            }
        }
        stage('Deploy') {
            steps {                
                        sh 'java -jar build/libs/hello-world-java-V1.jar'
                 }           
        }
    
}

post {
        always {
            echo 'Cleaning up workspace'
            deleteDir() // Clean up the workspace after the build
        }
        success {
            echo 'Build succeeded!!'
            // You could add notification steps here, e.g., send an email
        }
        failure {
            echo 'Build failed!!'
            // You could add notification steps here, e.g., send an email or Slack message
        }
    }
    }


