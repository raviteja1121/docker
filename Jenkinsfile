pipeline {
agent any
environment {
registry="raviteja1121/apache"
  }
stages { 
stage('dockerbuild') {
  steps {
    script {
      myImage=docker.build registry+":$BuildNumber"
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
