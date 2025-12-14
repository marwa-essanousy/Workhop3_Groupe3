pipeline {
    agent any

    environment {
        SONAR_HOST_URL = 'http://localhost:9000'
        SONAR_TOKEN    = 'sqp_88eb03682b0d3a1749d1018618baee70a826b4bf'   // ❗better to use Jenkins credentials later
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/marwa-essanousy/DevSecOps.git'
            }
        }

        stage('Install dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Run tests with coverage') {
            steps {
                bat 'set NODE_ENV=test&& npm test'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                script {
                    bat """
                  C:\\sonar-scanner\\bin\\sonar-scanner.bat ^
                  -Dsonar.host.url=%SONAR_HOST_URL% ^
                  -Dsonar.login=%SONAR_TOKEN%
"""
                }
            }
        }
    }
}
