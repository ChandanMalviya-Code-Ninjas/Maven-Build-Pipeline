pipeline {
    agent any
    
    tools {
        maven 'M3' // Make sure 'Maven' is configured in Jenkins
    }
    
    parameters {
        string(name: 'CGPA', defaultValue: '', description: 'Enter your CGPA')
    }
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ChandanMalviya-Code-Ninjas/Maven-Build-Pipeline.git' // Replace with your GitHub repo URL
            }
        }
        
        stage('Build') {
            steps {
                // Use 'bat' for Windows instead of 'sh'
                bat 'mvn clean compile'
            }
        }
        
        stage('Run App') {
            steps {
                // Use 'bat' and Windows-specific command for running Java application
                bat 'mvn exec:java -Dexec.mainClass="com.example.App"'
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline executed successfully.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
