pipeline {
    agent any

    tools {
        maven "M398"
    }

    stages {
        stage('Echo version') {
            steps {
                sh 'echo Print Maven version'
                sh 'mvn -version'
            }
        }

        stage('Build') {
            steps {
                // Get some code from a GitHub repo
                git branch: 'main', url: 'https://github.com/Keji-dev/jenkins-hello-world.git'

                // Run Maven Package CMD
                sh 'mvn clean package -DskipTests=true'
            }
        }

        stage('Unit Test') {
            steps {
                script {
                    for (int i = 0; i < 60; i++) {
                        echo "$(i + 1)"
                        sleep 1
                    }
                }
                sh 'mvn test'
            }    
        }
    }
}
