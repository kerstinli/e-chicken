node {
    checkout scm

    docker.withRegistry('192.168.8.10:5000') {

        docker.image('e-chicken-cinema').inside {
            sh 'make test'
        }
    }
}
