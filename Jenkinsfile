pipeline {
    agent any
    tools {
        jdk('jdk17')
    }
    
    stages {
        stage('Build') { 
            steps {
                 bat 'mvnw.cmd -B -DskipTests clean package' 
            }
        }
    }
}
