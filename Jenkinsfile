node {
    checkout scm

    stage 'Pull latest image from private-registry-1'

    def image
    docker.withRegistry('http://192.168.8.10:5000') {
        image = docker.image('e-chicken-cinema:latest')
        image.pull()
    }

    stage ('image build and Push') {
      steps {
        sh '''
            docker build -t e-chicken-cinema:latest .
            docker push e-chicken-cinema
            docker run -d -p 1234 e-chicken-cinema
        '''
      }
    }

}
