pipeline {
    agent any
    environment {
        def jsonContent = readFile(file: 'path/to/your/json/file.json')
        def json = readJSON(text: jsonContent)
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
