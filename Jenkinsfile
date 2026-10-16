pipeline {
    agent any

    options {
        timestamps()
        timeout(time: 10, unit: 'MINUTES')
    }

    stages {
        stage('Build') {
            steps { sh 'sh scripts/compile.sh' }
        }
        stage('Tests') {
            steps { sh 'sh scripts/verify.sh' }
        }
    }

    post {
        success { echo 'NOTIF : beta OK' }
        failure { echo 'NOTIF : beta KO' }
    }
}
