
pipeline {

  agent {
    docker { image 'node:8-alpine' }
  }

  stages {

    stage('Test Stage') {
      steps {
        def gitConf = checkout scm
        echo "Build ID ${env.BUILD_NUMBER} ${gitConf.GIT_BRANCH} ${env.WORKSPACE} ${gitConf.GIT_COMMIT}"
        sh 'cat package.json'
        def packageProps = readJSON file: 'package.json'
        echo "see version ${packageProps.version}"
        sh 'node -v'
      }
    }
    
  }

}
