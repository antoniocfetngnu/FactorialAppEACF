pipeline {
    agent any

    stages {
        stage('Clonar') {
            steps {
                git branch:"main" , url:'https://github.com/antoniocfetngnu/FactorialAppEACF.git'
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