node{
  stage('SCM Checkout'){
    git 'https://github.com/ashishtkumar/my-app'
  }
  stage('Compile Package'){
    sh 'mvn package' 
  }
}
