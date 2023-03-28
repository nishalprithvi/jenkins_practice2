pipeline {

    agent any
    stages {
            stage('BUILD'){
            steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/prithvinishal/jenkins_practice2.git/']])
                sh 'pwd'
                sh 'ls'
                sh 'whoami'
            }
        }
            
            stage('Building node application'){
            steps{
                echo "building the node application"
                sh 'npm install' // building the node application by setting up the npm library
            }
        }    
        
            stage('Building Docker Image') {
                steps {
                    script {
                        sh 'docker build -t node-app -f Dockerfile .'
                        sh 'docker images'
                        sh 'docker run -d node-app' //yeh run wala abhi smjhna hai ki isko kaise execute kiya jaye sahi se, abhi yaha pe execute krne se yeh unstoppable way mein run krta chala gya 
                            // although not a good practice to run docker image here image should be run on deployment server
                    }
                }
            }
            
        }
    }
