def slave = "aws-agents"
stage: "Print Hello"
node(slave) {
  checkout scm
  withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'public-git',
                          usernameVariable: 'user', passwordVariable: 'pass']]) {
    def user = env.user
    def pass = env.pass
    def url = 'kalpesh6641/github-wiki-image'
    def authenticatedGitRepo = "https://" + user + ":" + pass  + "@" + url
    sh """
      mkdir img
      cd img
      echo 'test' > test.txt
      git status
      git add .
      git commit -m "add test file"
      git push origin HEAD
    """
  }
  echo "hello"
}
