pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: "https://github.com/ishu162002/Banking-java-project.git"
                 echo 'github url checkout'
            }
        }
        stage('codecompile with ishu'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with ishu'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with ishu'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with ishu'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c000 myimg'
            }
        }   
    }
}
