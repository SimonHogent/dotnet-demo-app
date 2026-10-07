node {
    stage('Checkout') {
        checkout scm
    }
    stage('Preparation') {
        catchError(buildResult: 'SUCCESS', stageResult: 'SUCCESS') {
            sh 'docker compose down'
        }
    }
    stage('Build') {
        sh 'docker compose up -d --build'
    }
}