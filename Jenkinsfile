import groovy.json.JsonSlurper
// pipeline {
//     agent any
//     environment {
//         def jsonContent = readFile(file: 'sample.json')
//         def json = readJsonSlurper(text: jsonContent)
//     }
//     stages {
//         stage('Read JSON File') {
//             steps {
//                 script {
//                     def regions = json.regions
//                     regions.each { region ->
//                         echo "Region: ${region.name}"
//                         echo "Enabled: ${region.enable}"
//                     }
//                 }
//             }
//         }
//     }
// }

node {
  environment {
    def jsonContent = readFile(file: 'sample.json')
    def json = new groovy.json.JsonSlurper().parseText(jsonContent)
  }
  stage('Read JSON File') {
    // Iterate over the regions
    json.regions.each { region ->
      echo "Region: ${region.name}"
      echo "Enabled: ${region.enable}"
    }
  }
}
