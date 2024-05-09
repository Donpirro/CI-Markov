pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                
                git 'https://github.com/Donpirro/CI-Markov.git'
            }
        }
        stage('Build') {
            steps {
                // Paso para instalar dependencias de Python
                sh 'pip install -r requirements.txt'
                // Otros pasos de construcción, como compilación o empaquetado
                sh 'python setup.py build'
            }
        }
        stage('Test') {
            steps {
                // Paso para ejecutar pruebas unitarias y de integración
                sh 'pytest'
            }
        }
        stage('SonarQube Analysis') {
            steps {
                // Paso para ejecutar análisis de SonarQube
                withSonarQubeEnv('SonarQube') {
                    sh 'sonar-scanner'
                }
            }
        }
    }
}
