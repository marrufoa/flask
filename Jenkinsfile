pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/marrufoa/flask', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t marrufoa/flask_app .'
      }
    }

    stage('Docker Login') {
      steps {
        sh 'docker login -u marrufoa -p dckr_pat_l7nWwJC2Tn2t4Kr033m8yIFH72g'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push marrufoa/flask_app'
      }
    }

  }
}