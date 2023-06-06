pipeline {
    agent any
    environment {
        def jsonContent = readFile(file: 'sample.json')
        def json = readJSON(text: jsonContent, asMap: true)
    }
    stages {
        stage('Read JSON File') {
            steps {
                script {
                    def regions = json.get('regions')
                    if (regions != null) {
                        regions.each { region ->
                            echo "Region: ${region.name}"
                            echo "Enabled: ${region.enable}"
                        }
                    } else {
                        echo "No regions found in JSON file."
                    }
                }
            }
        }
    }
}
