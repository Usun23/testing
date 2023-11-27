pipeline {
    agent { 
        node {
            label 'Docker1'
            }
      }
    triggers {
        pollSCM '*/5 * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                sudo -s
                curl -O https://storage.googleapis.com/golang/go1.13.5.linux-amd64.tar.gz
                tar -xvf go1.13.5.linux-amd64.tar.gz
                mv go /usr/local
                echo "export PATH=$PATH:/usr/local/go/bin >> ~/.profile
                source ~/.profile
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                go version
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}
