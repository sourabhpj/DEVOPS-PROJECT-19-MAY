pipeline {
    agent any
    stages {
        stage(checkout) {
            step {
                  checkout scm
            }
        }
         stage(Build) {
            step {
                  sh 'docker build -t my-nginx-image .'
            }
        }
         stage(Deploy) {
            step {
                sh 'docker rm my-nginx-image || true'
                sh 'docker stop my-nginx-image || true'
                sh 'docker run -d --name my-nginx-image -p 80:80 my-nginx-image'

            }
        }

    }
}