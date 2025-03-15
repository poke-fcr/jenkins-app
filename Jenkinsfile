pipeline {
    agent any

    environment {
        VERCEL_ORG_ID = "pokefcrs-projects"
        VERCEL_PROJECT_ID = "prj_xi9TntSFyCFBeymR5QCLLomaGmbw"
    }

    stages {

        stage("Install Dependencies") {
            steps {
                bat 'npm install'  // For Windows
                // sh 'npm install'  // For Linux
            }
        }

        stage("Build Angular App") {
            steps {
                bat 'npm run build --configuration=production'
            }
        }

        stage("Deploy to Vercel") {
            steps {
                withCredentials([string(credentialsId: 'VERCEL_TOKEN', variable: 'VERCEL_TOKEN')]) {
                    bat "vercel --token %VERCEL_TOKEN% --prod --confirm"
                }
            }
        }
    }
}
