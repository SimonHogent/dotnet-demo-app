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
    stage('Database schema') {
        sh 'docker exec -i todoappdb mariadb -utodo_usr -pletmeinplz todo_db < TodoApp/schema.sql'
    }
}