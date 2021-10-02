pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }

    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }

        // Stage3 : Publish the source code to Nexus
        stage ('Publish to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.5.war', type: 'war']], credentialsId: 'fceb77d5-0faa-400b-8921-750f84f130f9', groupId: 'com.vinaysdevopslab', nexusUrl: '172.20.10.50:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'VinayDevops-SNAPSHOT', version: '0.0.5'
                }

            }
        }

        
        
    }

}