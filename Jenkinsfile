pipeline{
        agent any
        stages{
            stage('Clone Repository'){
                steps{
                     sh "mkdir ~/new"
                     sh "mv install_docker_compose.sh ~/new/install_docker_compose.sh"
                     sh "cd ~/new/"    
                     sh "chmod +x install_docker_compose.sh"
                     sh "git clone https://gitlab.com/qacdevops/chaperootodo_client"
                }
            }
            stage('Install Docker and Docker-Compose'){
                steps{
                     sh "./install_docker_compose.sh"
                }
            }
            stage('Desploy'){
                steps{
                     sh "sudo docker-compose up -d"
                }
            }
        }
}
