node
{
 
  stage("CheckOutCodeGit")
  {
   git credentialsId: 'git-cred', url: 'https://github.com/rahulbhange/new-node.git'
  }

  stage("codebuild")
   {
   nodejs('node-js') {
     sh 'npm install'}
   }
   
  stage("sonarqubescanner")
  {
   nodejs('node-js') {
     sh 'npm run sonar'}
  }
  
  stage("nexus-repo")
  {
   nodejs('node-js') {
     sh 'npm publish'}
  }
  
  stage("start-app")
  {
   nodejs('node-js') {
     sh 'npm start &'}
  }


}