pipeline {
agent any
environment {
registry="raviteja1121/apache"
docker_hub=credentials('dockerhub')
  }
stages { 
stage('dockerbuild') {
  steps {
    script {
      myImage=docker.build registry+":$BUILD_NUMBER"
    }
  }
}
stage('dockerpush') {
  steps {
    script {
      docker.withRegistry("https://hub.docker.com", "docker_hub") {
        myImage.push()
      }
    }
  }
}
}
}
