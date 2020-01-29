pipeline{
    agent{
        any
        environment{
            DOCKER_TAG = getDockerTag()
        }
        stages{
        stage("Build Docker Image"){
            steps{
                sh "docker build -t . fsaito/hello-world:${DOCKER_TAG}"
            }
        }
    }
}
    def getDockerTag(){
        def tag = sh script: 'git rev-parse HEAD', return$tdout: true
        return tag
    }
