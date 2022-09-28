pipeline {
    agent any
    tools {
        jdk('jdk17')
    }
    
    stages {
        stage('Build') { 
            steps {
                 bat 'mvnw.cmd -q -B -DskipTests clean package' 
            }
        }
        stage('Test') {
            steps {
                bat 'mvnw.cmd test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') { 
            steps {
                pwsh '.\\jenkins\\scripts\\deliver.ps1' 
            }
        }
    }
}
