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
                    echo region1
                    echo "Enable value for region ${json.regions[0].name}: ${json.regions[0].enable}"
                }
            }
        }
    }
}
