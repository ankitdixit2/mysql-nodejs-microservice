def notifySlack(String buildStatus = 'STARTED') {
    // Build status of null means success.
    buildStatus = buildStatus ?: 'SUCCESS'
    
    def msg = "${buildStatus}: `${env.JOB_NAME}` #${env.BUILD_NUMBER}:-Microservice image pushed to Docker registry by shrilekha.s"

    slackSend(message: msg)
}
node {
    checkout scm
    stage('build') {
        /* Test docker  compose */
            sh "sudo docker-compose build"
            sh "sudo docker tag mysqlnodejsmicroservice_db ankurdixit82/mysqlnodejsmicroservice_db:latest"
            sh "sudo docker tag mysqlnodejsmicroservice_users-service ankurdixit82/mysqlnodejsmicroservice_users-service:latest"
            sh "sudo docker push ankurdixit82/mysqlnodejsmicroservice_db:latest"    
            sh "sudo docker push ankurdixit82/mysqlnodejsmicroservice_users-service:latest"
            
    }
     try {
      
        notifySlack(currentBuild.result)

        // Existing build steps.
    } catch (e) {
        currentBuild.result = 'FAILURE'
        throw e
    }
}
