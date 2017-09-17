

node {
    
   
                    
        stage('Build binaries'){
            checkout scm
//            steps{
//              bat 'mvn clean install'
//            }
            
            def server = Artifactory.server "ART"
            def rtMaven = Artifactory.newMavenBuild()
            def buildInfo = Artifactory.newBuildInfo()
            rtMaven.tool = MAVEN_TOOL
            rtMaven.deployer releaseRepo:'libs-release-local', snapshotRepo:'libs-snapshot-local', server: server
            rtMaven.resolver releaseRepo:'libs-release', snapshotRepo:'libs-snapshot', server: server
            rtMaven.run pom: 'pom.xml', goals: 'clean install', buildInfo: buildInfo
            buildInfo.retention maxBuilds: 10, maxDays: 7, deleteBuildArtifacts: true
            // Publish build info.
            server.publishBuildInfo buildInfo
      }
   
}