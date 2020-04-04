node {
  stage('SCM') {
    echo 'Gathering code from version control'
    git branch: '${branch}', url: 'https://github.com/FeynmanFan/JenkinsGroovy.git'
  }
  stage('Build') {
    try{
      echo 'Building..'
      releasnotes()
    }catch(ex) {
      echo 'Something went wrong'
      echo ex.toString();
      currentBuild.result = 'FAILURE'
    }finally{
      //cleanup
    }
  }
  stage('Test') {
    echo 'Testing..'
  }
}
