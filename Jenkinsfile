pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    userRemoteConfigs: [[
                        url: 'https://github.com/keysersoze12/SIT753-Task6.1C.git',
                        credentialsId: '5561bb68-438c-41b8-b082-d0044ad8cc05'
                    ]]
                ])
            }
        }

        stage('Build') {
            steps {
                echo 'No build required for this dummy project. Skipping build stage.'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running dummy tests...'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Running dummy code analysis...'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Running dummy security scan...'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying dummy project to staging...'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying dummy project to production...'
            }
        }
    }

    post {
        success {
            mail to: 's223859001@deakin.edu.au',
                 subject: "SUCCESS: Build ${currentBuild.fullDisplayName}",
                 body: """The Jenkins job ${env.JOB_NAME} was successful.
                          Job URL: ${env.BUILD_URL}"""
        }
        failure {
            mail to: 's223859001@deakin.edu.au',
                 subject: "FAILURE: Build ${currentBuild.fullDisplayName}",
                 body: """The Jenkins job ${env.JOB_NAME} failed.
                          Job URL: ${env.BUILD_URL}"""
        }
    }
}
