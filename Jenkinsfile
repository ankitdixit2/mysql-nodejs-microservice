node {
    checkout scm
    stage('build') {
        /* Test docker  compose */
            sh "docker-compose build"
            sh "docker-compose up"
    }
}
