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
                    def regions = json.regions
                    regions.each { region ->
                        echo "Region: ${region.name}"
                        echo "Enabled: ${region.enable}"
                    }
                }
            }
        }
    }
}
