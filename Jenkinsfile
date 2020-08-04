pipeline {
    agent any
    options {
        buildDiscarder(logRotator(numToKeepStr: '5'))
        timeout(time: 10, unit: 'MINUTES')
        timestamps()  // Timestamper Plugin
        disableConcurrentBuilds()
    }
    tools{
        jdk 'jdk8'
        maven 'maven35'
    }
     stages {
        stage('Build') {
            steps {
                echo "start..... triggger trigger"
                sh 'mvn -B -V -U -e clean verify -Dsurefire.useFile=false'
                archiveArtifacts 'target/*.?ar'
                junit 'target/**/*.xml'  // Requires JUnit plugin
            }
        }
    }
}
