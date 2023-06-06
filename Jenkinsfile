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
  stage('Read JSON File') {
    def jsonContent = readFile(file: 'sample.json')
    def json = new groovy.json.JsonSlurper().parseText(jsonContent)
    // Iterate over the regions
    json.regions.each { region ->
      echo "Region: ${region.name}"
      echo "Enabled: ${region.enable}"
    }
  }
}
