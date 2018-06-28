node {
    checkout scm
    stage('build') {
        /* Test docker  compose */
            sh "docker-compose build"
            sh "docker tag mysqlnodejsmicroservice_db ankurdixit82/mysqlnodejsmicroservice_db:latest"
            sh "docker tag mysqlnodejsmicroservice_users-service ankurdixit82/mysqlnodejsmicroservice_users-service:latest"
            sh "docker push mysqlnodejsmicroservice_db:latest"    
            sh "docker push mysqlnodejsmicroservice_users-service:latest"
            
    }
}
