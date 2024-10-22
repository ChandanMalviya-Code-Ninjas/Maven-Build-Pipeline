pipeline {
    agent any
    stages {
        stage('clone repo & clean') {
            steps {
                bat 'if exist "Maven-Build-Pipeline" rmdir /S /Q "Maven-Build-Pipeline"'  // Check if directory exists before deleting
                bat "https://github.com/ChandanMalviya-Code-Ninjas/Maven-Build-Pipeline.git"
                bat "mvn clean -f Maven-Build-Pipeline"
            }
        }
        stage('Test') {
            steps {
                bat "mvn test -f Maven-Build-Pipeline"
            }
        }
        stage('Deploy') {
            steps {
                bat "mvn package -f Maven-Build-Pipeline"
            }
        }
    }
}
