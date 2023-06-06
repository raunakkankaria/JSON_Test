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
                        def enabledRegions = json.regions.findAll { region ->
                            region.enable == true
                        }

                        enabledRegions.each { region ->
                            echo "Enable value for region ${region.name}: ${region.enable}"
                        }
//                         json.regions.each {
//                         echo "Enable value for region ${region.name}: ${region.enable}"
//                             
//                     }
                }
            }
        }
    }
}
