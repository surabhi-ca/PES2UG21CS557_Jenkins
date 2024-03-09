pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
              checkout([$class: 'GitSCM',
                        branches:[[name: '*/main']],
                        userRemoteConfigs: [[url: 'https://github.com/surabhi-ca/PES2UG21CS557_Jenkins.git']]])
            }
        }
        stage('Build') {
            steps {
                // Replace this step with the actual build command for your project
                // This example compiles a C++ program named 'main.cpp'
              build 'PES2UG21CS557_1'
                sh 'g++ main.cpp -o output'
            //}
        }
        stage('Test') {
            steps {
                // Replace this step with the actual command to run your tests
                sh './output' // Assuming the compiled program is named 'output'
            }
        }
        stage('Deploy') {
            steps {
                // Replace this step with the actual deployment commands
                echo 'Deployment'
            }
        }
    }

    post {
        failure {
            // Set a custom failure message
            echo 'Pipeline failed!'
        }
    }
}
