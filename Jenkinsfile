pipeline {
    agent any
    options {
        buildDiscarder(logRotator(numToKeepStr: '5'))
        timeout(time: 10, unit: 'MINUTES')
        timestamps()  // Timestamper Plugin
        disableConcurrentBuilds()
    }
    environment{
        GRETINGS_TO = 'Jenkins Techlab'
    }
    stages {
        stage('Greeting') {
            steps {
                echo "Hello ${env.GREETINGS_TO}"
                sh 'echo "Hello $GREETINGS_TO (from command)"'
            }
        }
    }
}
