node {
    checkout scm

    stage 'Pull latest image from private-registry-1'

    def image
    docker.withRegistry('http://192.168.8.10:5000') {
        image = docker.image('e-chicken-cinema:latest')
        image.pull()
    }

    stage 'Push image to private-registry-2'

    // SOLUTION START
    sh 'docker tag 192.168.8.10:5000/e-chicken-cinema:latest 192.168.8.210:5000/e-chicken-cinema:latest'
    image = docker.image('192.168.8.210:5000/e-chicken-cinema:latest')
    // SOLUTION END

    docker.withRegistry('http://192.168.8.210:5000') {
        image.push()
    }    
    
}
