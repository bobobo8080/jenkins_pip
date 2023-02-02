pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Goodbye'){
            steps {
                echo 'Goodbye'
                mail bcc: '', body: 'Im inside my step', cc: '', from: '', replyTo: '', subject: 'Step message', to: 'benlahav2@gmail.com'
            }
        }

    }
    post{
            success{
                mail bcc: '', body: 'This time everything is good.', cc: '', from: '', replyTo: '', subject: 'Successful build', to: 'devboss7878@gmail.com'
            }
            failure{
                step([$class: 'Mailer', notifyEveryUnstableBuild: true, recipients: 'benlahav2@gmail.com', sendToIndividuals: false])
            }
    }
}
