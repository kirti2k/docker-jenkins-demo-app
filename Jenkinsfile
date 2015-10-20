node {
  stage 'build'
  docker.image('kohsuke/acmecorp-buildenv').inside {
    git 'https://github.com/kirti2k/docker-jenkins-demo-app.git'
    sh 'mvn install'
    archive 'target/*.war'
  }

  stage 'package'
  docker.build('kirti2k/docker-jenkins-demo').push()

  stage 'deploy'
  sh './deploy.sh'
}
