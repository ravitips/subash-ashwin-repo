pipeline{
    agent any
    stages{
        stage('build'){
            steps{
                sh """
                    sudo cat index.html > /var/www/html/index.nginx-debian.html
                """
            }
        }
        
        stage('deploy'){
            steps{
                sh """
                    sudo systemctl restart nginx
                """
            }
        }
        
    }
}
