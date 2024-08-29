pipeline {
    agent any
    
    stages {
        stage('Clean workspace and Navigate to the folder'){
            steps{
                cleanWs()
            }
        }
        stage('Build') {
            steps {
                bat 'javac Pattern.java'
            }
        }
        stage('Jar') {
            steps {
                bat 'jar cfe myJar.jar Pattern Pattern.class'
            }
        }
        stage('Run') {
            steps {
                bat 'java -jar myJar.jar'
            }
        }
        stage('Artifact'){
            steps{
                archiveArtifacts artifacts: '*.jar', followSymlinks: false
            }
        }
    }
}
