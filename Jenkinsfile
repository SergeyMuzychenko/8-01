pipeline {
 agent any
 stages {
  stage('Git') {
   steps {
    git 'https://github.com/SergeyMuzychenko/sdvps-materials'
   }
  }
  stage('Test') {
   steps {
    sh '/usr/local/go/bin/go test .'
   }
  }
  stage('Build') {
   steps {
    sh 'docker build . -t ubuntu:6463/hello-world:v$BUILD_NUMBER'
   }
  }
 }
}
