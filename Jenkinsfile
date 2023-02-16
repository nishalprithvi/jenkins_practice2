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
            

            stage('Building Docker Image') {
                steps {
                    script {
                        sh 'docker build -t node-app -f Dockerfile .'
                        sh 'docker images'
                        //sh 'docker run node-app' yeh run wala abhi smjhna hai ki isko kaise execute kiya jaye sahi se, abhi yaha pe execute krne se yeh unstoppable way mein run krta chala gya 
        
                    }
                }
            }
            
        }
    }