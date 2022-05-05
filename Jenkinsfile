pipeline {
    agent any
    
    environment {
    DOCKER_CERT_PATH = credentials('dockerhub')
  }
    
    stages {
        stage('Welcome Step') {
            steps { 
                echo 'Welcome to LambdaTest'
            }
        }
        stage('binary Build'){
            steps {
                sh 'echo $PATH'
//                 sh 'go mod tidy'
//                 sh 'go build main.go'
            }
        }
        stage('build') {
            steps {
                sh 'docker build -t ibackchina2018/golang-app-jenkins-demo:latest .' 
             }
        }
        
//         stage('Login') {
//             steps {
//                 sh 'chmod +x ./scripts/login.sh'
//                 sh './scripts/login.sh'
//             }
//         }
        
//         stage('Pushing docker image to docker hub') {
//             steps {
//                 withCredentials([string(credentialsId: 'dockerhub', variable: 'dockerHubPasswd')]) {
//                      sh  '''
//                         set +x
//                         docker login -u ibackchina2018 -p "${dockerHubPasswd}  https://index.docker.io/v1/"
//                     '''
//                 }
//             }
//         }
            
        stage('Push') {
            steps {
                sh 'docker push ibackchina2018/golang-app-jenkins-demo:latest'
            }
        }

        
        

    }
}
