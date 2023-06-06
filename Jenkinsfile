import groovy.json.JsonSlurper

pipeline {
    agent any
    environment {
        def jsonContent = readFile(file: 'sample.json')
        def json = new JsonSlurper().parseText(jsonContent)
    }
    stages {
        stage('Read JSON File') {
            steps {
                script {
                        json.regions.each { region ->
                        echo "Enable value for region ${region.name}: ${region.enable}"
                    }
                }
            }
        }
    }
}
