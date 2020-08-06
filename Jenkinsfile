pipeline {
    agent any
    options {
        buildDiscarder(logRotator(numToKeepStr: '5'))
        timeout(time: 20, unit: 'MINUTES')
        timestamps()  // Timestamper Plugin trigger
        disableConcurrentBuilds()
    }
    tools{
        jdk 'jdk11'
        maven 'maven35'
    }
     stages {
        stage('Build') {
            steps {
                sh '$JAVA_HOME/bin/javac -version'
                sh 'mvn -B -V -U -e clean verify -Dsurefire.useFile=false -DargLine="-Djdk.net.URLClassPath.disableClassPathURLCheck=true"'
                archiveArtifacts 'target/*.?ar'
                junit 'target/**/*.xml'  // Requires JUnit plugin
            }
        }
    }
}
