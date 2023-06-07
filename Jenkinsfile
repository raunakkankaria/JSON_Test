node {
  stage('Checkout from Git') {
    checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/raunakkankaria/JSON_Test.git']])
  }
  stage('Read JSON File') {
    // Read the JSON file
    def jsonContent = readFile(file: 'sample.json')
    def json = new groovy.json.JsonSlurper().parseText(jsonContent)
    
    // Iterate over the regions
    json.regions.each { region ->
      echo "Region: ${region.name}"
      echo "Enabled: ${region.enable}"

      // Export the region name to environment
      env.REGION_NAME = region.name

      // Export the region enabled status to environment
      env.REGION_ENABLED = region.enabled
    }
  }

  // Use the region name and enabled status in subsequent stages
  stage('Deploy to Region') {
    // Deploy to the region with the specified name
    sh "echo Deploying to region ${env.REGION_NAME}"

    // Check if the region is enabled
    if (env.REGION_ENABLED == true) {
      sh "echo Region is enabled"
    } else {
      sh "echo Region is not enabled"
    }
  }
}
