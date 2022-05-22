Pipeline {
    agent {any}
    triggers { cron('0 * * * *') }
    stages {
        stage ('Source Code') {
            steps {
                //get the source code from the git repository
            git url: 'https://github.com/KrishnaV94/game-of-life.git'
            branch: 'master'
            }
        }
        stage ('Build the code') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage ('Reports') {
            steps {
                junit testResults: '**/surefire-reports/*.xml'
            }
        }
        }
    }
    post {
        success {
            //Send the Success notification
            echo 'Successful'
        }
        unsuccessful {
            //Send the unsuccessful notification
            echo 'Unsuccessful'
        }
    }
}