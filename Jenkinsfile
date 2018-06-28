node {
    checkout scm
    stage('build') {
            sh "docker-compose build"
            sh "docker-compose up"
    }
}
