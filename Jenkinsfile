node {
    checkout scm
    stage('build') {
        /* Test docker  compose */
            sh "docker-compose build"
            sh "docker push mysql" 
            sh "docker push node"
            sh "docker push dockermicroservive_users-service"
            sh "docker push dockermicroservive_db"
    }
}
