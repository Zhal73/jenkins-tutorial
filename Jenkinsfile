pipeline{
        agent any
        stages{
            stage('Clone Repository'){
                steps{
                     sh "mkdif ~/repo-tutotial-2 && cd $_"
                     sh "mv install_docker_compose.sh ~/repo-tutotial-2/install_docker_compose.sh"
                     sh "chmod +x install_docker_compose.sh"
                     sh "git clone https://github.com/Zhal73/jenkins-tutorial.git"
                }
            }
            stage('Install Docker and Docker-Compose'){
                steps{
                     sh "curl https://get.docker.com | sudo bash"
                     sh ". ./install_docker_compose.sh"
                }
            }
            stage('Desploy'){
                steps{
                     sh "sudo docker-compose up -d"
                }
            }
        }
}
