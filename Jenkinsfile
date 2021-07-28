node{
  stage('SCM Checkout'){
    git branch: 'main', url: 'https://github.com/ashishtkumar/my-app'
  }
  stage('Compile Package'){
    def mvnHome=tool name: 'maven3', type: 'maven'
    sh "${mvnHome}/bin/mvn package" 
  }
}
