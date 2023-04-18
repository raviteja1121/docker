pipeline {
agent any
environment {
registry="docker_first"
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
      docker.withRegistry('https://473834275811.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:raviaws') {
        myImage.push()
      }
    }
  }
}
}
}
