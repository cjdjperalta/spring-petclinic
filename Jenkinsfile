pipeline {
    agent any  // Runs on any available agent

    environment {
        MAVEN_HOME = tool 'Maven'  // Ensure Maven is installed in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/cjdjperalta/spring-petclinic.git'
            }
        }

        stage('Build') {
            steps {
                sh '${MAVEN_HOME}/bin/mvn clean package'
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
