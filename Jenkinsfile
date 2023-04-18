pipeline {
agent any
environment {
registry="raviteja1121/apache"
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
      docker.withRegistry("https://index.docker.io", "dockerhub") {
        myImage.push()
      }
    }
  }
}
}
}
