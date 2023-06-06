pipeline {
    agent any
    environment {
        def jsonContent = readFile(file: 'sample.json')
        def json = readJSON(text: jsonContent)
    }
    stages {
        stage('Read JSON File') {
            steps {
                script {
                        echo json
                        json.regions.each { region ->
                        echo "Enable value for region ${region.name}: ${region.enable}"
                    }
                }
            }
        }
    }
}
