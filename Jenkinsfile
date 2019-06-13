pipeline {
    agent any
    
    stages {
        stage('Preparation') {
            steps {
                echo 'Preparation'
            }
        }
        stage('Build') {
            steps {
                echo 'Build'
                sh './gradlew clean test jar'
            }
        }
        stage('Results') {
            steps {
                echo 'Results'
                
                archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
                junit '**/build/test-results/test/TEST-*.xml'
            }
        }
    }
}
