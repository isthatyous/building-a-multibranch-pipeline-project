pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
          stage('Deploy') {
    when {
        beforeAgent true
        branch 'development'
    }
    steps {
        sh './jenkins/scripts/deploy.sh'
    }
}

stage('Production') {
    when {
        beforeAgent true
        branch 'production'
    }
    steps {
        sh './jenkins/scripts/deploy.sh'
    }
}

    }
}
