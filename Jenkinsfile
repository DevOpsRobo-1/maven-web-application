node {
    
    properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])
    
    def mavenHome = tool name:"maven3.9.8"
    
    stage('CheckOutCode')
    {
       git branch: 'development', credentialsId: '2d95cb81-843b-4ee9-bbc5-2531d0e7a4d6', url: 'https://github.com/DevOpsRobo-1/maven-web-application.git'
    }
    
    stage('Build')
    {
        sh "${mavenHome}/bin/mvn clean package"
    }

  /*
    stage('ExecuteSonarQubeReport')
    {
        sh "${mavenHome}/bin/mvn sonar:sonar"
    }
    
    stage('UploadArtifactsIntoNexus')
    {
        sh "${mavenHome}/bin/mvn deploy"
    }
    
    stage('DeployAppIntoTomcat')
    {
        sshagent(['13124839-e8b4-477d-9ac4-e30f4d76b5cf']) {
        sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@10.42.1.148:/opt/apache-tomcat-9.0.95/webapps"
    }
    }

    */
    
}
