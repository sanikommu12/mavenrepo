pipeline {
  agent any
  stages {
    stage('scm') {
      steps {
        git(url: 'https://github.com/sanikommu12/mavenrepo.git', branch: 'master', credentialsId: 'Git123', poll: true)
      }
    }

    stage('Build') {
      steps {
        sh '/usr/share/maven/bin/mvn package'
      }
    }

    stage('QA') {
      steps {
        withSonarQubeEnv(installationName: 'sonar', credentialsId: '2133', envOnly: true) {
          sh '/usr/share/maven/bin/mvn sonar:sonar'
        }

      }
    }

  }
}