pipeline {
    agent any
    options {
        buildDiscarder(logRotator(numToKeepStr: '5'))
        timeout(time: 20, unit: 'MINUTES')
        timestamps()  // Timestamper Plugin trigger
        disableConcurrentBuilds()
    }
    tools{
        jdk 'jdk8'
        maven 'maven35'
    }
     stages {
        stage('Build') {
            steps {
                sh 'apt-get install ca-certificates-java'
                sh 'printenv'
                sh '$JAVA_HOME/bin/javac -version'
                echo "start..... triggger trigger"
                sh 'mvn -B -V -U -e clean verify -Dsurefire.useFile=false'
                archiveArtifacts 'target/*.?ar'
                junit 'target/**/*.xml'  // Requires JUnit plugin
            }
        }
    }
}
