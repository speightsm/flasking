pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/speightsm/flasking.git', branch: 'main')
      }
    }

    stage('Docker Build') {
      steps {
        sh 'docker build -t speightsm/flask_app .'
      }
    }

    stage('Docker Login') {
      steps {
        sh 'docker login -u speightsm -p dckr_pat_Gy6FM7bUsrxT4PtTlGIO0lgKMlE'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push speightsm/flask_app'
      }
    }

  }
}