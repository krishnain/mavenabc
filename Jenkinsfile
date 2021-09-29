node('master') 
{
    stage('ContinuousDownload_Master')
    {
        git 'https://github.com/krishnain/mavenabc.git'             
    }
    stage('ContinuousBuild_Master')
    {
        sh 'mvn package'
    }
    stage('ContinuousDeployment_Master')
    {
       deploy adapters: [tomcat9(credentialsId: '189a34cb-d927-4cac-b566-78fd44cea225', path: '', url: 'http://172.31.91.172:8080')], contextPath: 'qaapp', war: '**/*.war'
    }
    stage('ContinuousTesting_Master')
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline/testing.jar'
    }
    stage('ContinuousDelivery_Master')
    {
       deploy adapters: [tomcat9(credentialsId: '189a34cb-d927-4cac-b566-78fd44cea225', path: '', url: 'http://172.31.86.48:8080')], contextPath: 'prodapp', war: '**/*.war'
    }
}
