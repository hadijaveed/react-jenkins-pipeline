
def withCredentialsConf = [[
  $class: 'UsernamePasswordMultiBinding',
  credentialsId: 'test-creds',
  usernameVariable: 'USERNAME',
  passwordVariable: 'PASSWORD'
]]


node {
  withCredentials(withCredentialsConf) {
    echo 'Hello World'
    echo "check is docker is there ${docker}"
    echo "$env"
    stage('Test Stage') {
      checkout scm
      echo 'testing the stage here just'
      echo "Creds test $USERNAME and password test $PASSWORD"
      echo "Build ID ${env.BUILD_NUMBER} ${env.GIT_BRANCH} ${env.WORKSPACE} ${env.GIT_COMMIT}"
    }
  }
}