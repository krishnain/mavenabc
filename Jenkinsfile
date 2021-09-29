node('master') 
{
    stage('ContinuousDownload_Loans')
    {
        git 'https://github.com/krishnain/mavenabc.git'             
    }
    stage('ContinuousBuild_Loans')
    {
        sh 'mvn package'
    }
}
