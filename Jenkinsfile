node{
 def server = Artifactory.server "SERVER_ID"
 def rtGradle = Artifactory.newGradleBuild()
 def buildInfo
 
 stage('Checkout'){
  git 'https://github.com/saimanasranjan/JenkinTeting'
 }
 stage('Artifactory configuration') {
        rtGradle.tool = "Gradle-4.3"
        // Set Artifactory repositories for dependencies resolution and artifacts deployment.
        rtGradle.deployer repo:'ext-release-local', server: server
        rtGradle.resolver repo:'remote-repos', server: server
    }

    stage('Gradle build') {
        buildInfo = rtGradle.run rootDir: "JenkinTeting/demo/", buildFile: 'build.gradle', tasks: 'clean artifactoryPublish'
    }
}
