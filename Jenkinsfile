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
                    def region1 = json.regions[0]
                    echo "Enable value for region ${region1.name}: ${region1.enable}"
                }
            }
        }
    }
}
