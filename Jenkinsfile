pipeline {
  agent any
  stages {
    stage('scm') {
      steps {
        git(url: 'https://github.com/sanikommu12/mavenrepo.git', branch: 'master', changelog: true)
      }
    }

  }
}