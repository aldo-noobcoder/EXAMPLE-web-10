pipeline{
    agent any

    stages{
        stage("Build"){
            steps{
                echo "Building..."
            }
        }
        stage("Deploy"){
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps{
                sh '''
                    npm install netlify-cli -g
                    netlify --version
                '''
            }   
        }
    }
}