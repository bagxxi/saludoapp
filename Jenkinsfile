pipeline {
    agent any
    tools {
        maven 'Maven 3.9.10'
        jdk 'JDK21'
    }
        stages {
            stage('Clonar') {
            steps {
                checkout scm
                }
            }
            stage('Compilar') {
                steps {
                    bat 'mvn clean compile'
                }
            }
            stage('Probar') {
                steps {
                    bat 'mvn test'
                }
            }
            stage('Empaquetar') {
                steps {
                    bat 'mvn package'
                }
            }
        }
    post {
        success {
            echo "🎉 El build fue exitoso"
        }
        failure {
            echo "💥 El build falló"
        }
    }
}