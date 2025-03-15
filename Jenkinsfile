pipeline {
    agent any  // Runs on any available agent

    stages {
        stage("Build") {
            steps {
                script {
                    bat 'npm i'
                    bat 'npm run ng build'
                }
            }
        }
         stage("afterBuild") {
            steps {
                script {
                    echo "Hello, World! Jenkins Pipeline is running 2."
                }
            }
        }
    }
}
