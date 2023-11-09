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
    build '/usr/local/go/bin/go build -a -installsuffix nocgo -o /app .'
   }
  }
  stage('Push') {
   steps {
    sh 'docker login ubuntu-bionic:8082 -u admin -p admin && docker push ubuntu-bionic:8082/hello-world:v$BUILD_NUMBER && docker logout'   }
  }
 }
}
