node
{
    def mavenhome=tool name:'maven3.8.4',type:'maven'
      properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])
    stage('checkout clone'){
        git credentialsId: 'ff21682a-1c49-4982-a426-f88863aa3aab', url: 'https://github.com/sewtha0292/maven-web-application.git'
    }
    stage('build'){
        sh "${mavenhome}/bin/mvn clean package"
    }
    /*
    stage('sonarreport'){
        sh "${mavenhome}/bin/mvn sonar:sonar"
    }
    stage('artifactory repository nexus'){
         sh "${mavenhome}/bin/mvn deploy"
    }
    stage('deploy to container tomcat'){
        sshagent(['fc62ee03-a5cc-4dae-826c-1e1f47f1e3d4']) {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war  ec2-user@18.220.161.39:/opt/apache-tomcat-9.0.55/webapps/"
}
    }
    stage('email notification'){
        emailext body: '''


with regards:
subbu''', recipientProviders: [buildUser()], subject: 'build operation', to: 'subramanyam4all@gmail.com'
    }
    */
}
