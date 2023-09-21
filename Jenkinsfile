pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    def npmTool = tool name: 'NodeJS 14', type: 'Tool'
                    sh "${npmTool}/bin/npm install"
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    def npmTool = tool name: 'NodeJS 14', type: 'Tool'
                    sh "${npmTool}/bin/npm run build"
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    def npmTool = tool name: 'NodeJS 14', type: 'Tool'
                    sh "${npmTool}/bin/npm start"
                }
            }
        }
    }
}
