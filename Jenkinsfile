node {
    stage ('Staging') {

    sh 'ssh -l jenkins 172.18.0.3 "cd /usr/share/nginx/html && git checkout staging && git pull staging staging"'
  }
}
  stage('Deploy approval'){
    input "Deploy to prod?"
}
node {
    stage('deploy to prod'){
    sh 'ssh -l jenkins 172.18.0.4 "cd /usr/share/nginx/html && git checkout master && git pull prod staging"'
    }
}
