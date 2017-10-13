def slave = "aws-agents"
stage: "Print Hello"
node(slave) {
  checkout scm
  sh """
    mkdir img
    cd img
    echo 'test' > test.txt
    git status
    git add .
    git commit -m "add test file"
    git push origin HEAD
  """
  echo "hello"
}
