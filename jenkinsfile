node{

    properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('')])])
    
    def mavenHome = tool name: "maven3.8.4"
    
stage('CheckOutCode'){

git branch: 'development', credentialsId: '9ad07562-2748-4655-8b27-66d942b41179', url: 'https://github.com/dilee091993/maven-web-application.git'
}


stage('Build'){
sh "${mavenHome}/bin/mvn clean package"
}

 /*
stage('ExcuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn sonar:sonar"

}

stage('UploadArtifactIntoNexusRepo'){
sh "${mavenHome}/bin/mvn deploy"

}

stage('DeployAppIntoTomcatServer'){
sshagent(['44d1973c-3af9-4f6c-8890-c3ffd236ffd1']) {
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.111.171.161:/opt/apache-tomcat-9.0.63/webapps/" 
}

}
*/
}
