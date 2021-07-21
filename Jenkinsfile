node{
  stage('SCM Checkout'){
    git branch: 'main', url: 'https://github.com/ashishtkumar/my-app'
  }
  stage('Compile Package'){
    sh 'mvn package' 
  }
}
