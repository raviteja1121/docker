pipeline {
agent any
environment {
registry="raviteja1121/apache"
  }
tools { docker 'docker' }
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
      docker.withRegistry("https://registry.hub.docker.com", "dockerhub") {
        myImage.push()
      }
    }
  }
}
}
}
