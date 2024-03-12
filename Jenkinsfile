def COLOR_MAP = [
    'FAILURE' : 'danger',
    'SUCCESS' : 'good'
]

pipeline {
    agent any

    stages {
        stage('First') {
            steps {
                echo "This is 1st stage"
            }
        }
        stage('Second') {
            steps {
                echo "This is 2nd stage"
            }
        }
        stage('Third') {
            steps {
                echo "This is 3rd stage"
            }
        }
        stage('Fourth') {
            steps {
                echo "This is 4th stage"
            }
        }
        stage('Fifth') {
            steps {
                echo "This is 5th stage"
            }
        }
    }

    post {
        always {
            echo 'Slack Notification'
            slackSend channel: 'devops',
                color: COLOR_MAP[currentBuild.currentResult],
                message: "*${currentBuild.currentResult}:* Job ${env.JOB_NAME} build ${env.BUILD_NUMBER} \n More info at: ${env.BUILD_URL}"
        }
    }
}