pipeline {
    agent any
    
    tools {
        // Define Maven installation. Adjust the version if needed.
        maven 'Maven 3.8.1'
    }
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from Git repository
                git branch: 'main', url: 'https://github.com/lollaranga/star-agile-banking-finance.git'
            }
        }
        
        stage('Build') {
            steps {
                // Build the project using Maven
                sh './mvnw clean install'
            }
        }
        
        stage('Test') {
            steps {
                // Run tests using Maven
                sh './mvnw test'
            }
        }
        
        stage('Package') {
            steps {
                // Package the application
                sh './mvnw package'
            }
        }
        
        stage('Deploy') {
            steps {
                // Deploy steps (if any). Add your deployment logic here.
                echo 'Deploying the application...'
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
