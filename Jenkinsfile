pipeline{
    agent any
    parameters{
        string(name: 'SOURCE_FILE',description: 'Enter your webpage file name', defaultValue: 'index.html')
        string(name: 'DESTINATION_FILE',description: 'Enter your nginx file name', defaultValue: 'index.nginx-debian.html')
        string(name: 'FILE_PATH',description: 'Enter your destination file path', defaultValue: '/var/www/html')
        choice(name: 'SERVICE',choices: ['nginx','apache','docker'],description: 'Enter your service name')
    }
    stages{
        stage('build'){
            steps{
                sh """
                    sudo cat ${params.SOURCE_FILE} > ${params.FILE_PATH}/${params.DESTINATION_FILE}
                """
            }
        }
        
        stage('deploy'){
            steps{
                sh """
                    sudo systemctl restart ${params.SERVICE}
                """
            }
        }
        
    }
}
