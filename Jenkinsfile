pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/oficial-devops/mynewrepo1234/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with ajay'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with ajay'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with ajay'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with ajay'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t ajay/banking-project-demo:3.0 .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c000 ajay/banking-project-demo:3.0'
            }
        }   
    }
}
