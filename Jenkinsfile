pipeline {
    agent any
    parameters {
        string(name: 'company_parameter', defaultValue: 'puzzle', description: 'The company the pipeline runs in')
    }
    stages {
        stage('Build') {
            steps {
                script{
                    def company = "puzzle"
                    def member = "christian"

                    echo "Wilkommen bei der ${company}, \"${member}\""
                    echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL} in company ${parameter.company_parameter}"
                }
            }
        }
    }
}
