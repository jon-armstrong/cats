
node {
  
  stage 'checkout'
  scm checkout

  stage 'docker image build'
  def VERSION = readFile('VERSION').trim()
  def image = docker.build('mikesir87/cats:' + VERSION)

  stage 'docker push'
  docker.withRegistry('https://hub.docker.com/', 'docker-hub') {
    image.push(VERSION);
  }
}

