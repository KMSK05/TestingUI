pipeline {
    agent any  // Adjust if needed (e.g., specific docker image)

    stages {
        stage('Checkout Code') {
            steps {
                script {
                    // Checkout code from your version control system (e.g., Git)
                    git branch: 'master', credentialsId: 'your-git-credentials-id', url: 'https://github.com/KMSK05/TestingUI.git'
                }
            }
        }
        stage('Build Application') {
            steps {
                // Build your application code (replace with your build commands)
                sh 'mvn clean install'  // Example for Maven project
            }
        }
        stage('Run Selenium Tests') {
            steps {
                // Run your Selenium tests within a Docker container
                sh 'docker run your-test-container-image mvn test' // Replace with your commands
            }
        }
        stage('Publish Test Results') {
            steps {
                // Publish test results (e.g., JUnit reports)
                junit '/target/surefire-reports/*.xml'
            }
        }
    }
}
