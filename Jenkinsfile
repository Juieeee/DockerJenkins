pipeline{
  agent any
  stages{
    stage('checkout){
          steps{
            git url:'https://github.com/Juieeee/DockerJenkins.git'
          }
          }

          stage('Build Image'){
            steps{
              bat 'docker build -t mywebsite .'
            }
          }
          
          stage('Stop Old Containers'){
            steps{
              bat 'docker stop mycont || exit 0'
              bat 'docker rm mycont || exit 0'
            }
          }

          stage('Run Image -Contanerize'){
            steps(
              bat 'docker run -d -p 7000:80 --name mycont mywebsite'
              }
           }
        }
        }
                        
              
