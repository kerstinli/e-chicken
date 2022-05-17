node {
    checkout scm

    docker.withRegistry('http://192.168.8.10:5000') {

        docker.image('e-chicken-cinema').inside {
            sh 'make test'
        }
    }
}
