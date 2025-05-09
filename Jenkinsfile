pipeline {
    agent any
    tools {
        maven 'Maven 3.8.5'    // Nombre del Maven configurado en Jenkins
        jdk 'Java 11'          // Nombre del JDK configurado
    }
    stages {
        stage('Clonar') {
            steps {
                git 'https://github.com/antoniocfetngnu/FactorialAppEACF.git'
            }
        }
        stage('Compilar') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('Pruebas') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Empaquetar') {
            steps {
                sh 'mvn package'
            }
        }
    }
    post {
        success {
            echo 'Build y pruebas exitosas'
        }
        failure {
            echo 'Falló el proceso'
        }
    }
}
v