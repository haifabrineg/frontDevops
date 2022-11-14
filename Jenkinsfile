
pipeline {
    agent any
   tools {nodejs "NodeJS"}
   
    stages{
       
     
        stage('Init'){
            steps{
                script{
                    sh 'npm install --force'
                }
            }
        }
        stage('Compile'){
            steps{
                script{
                    sh 'ng build'
                }
            }
        }
        
        
     
        stage('Build And Deploy Docker Image'){
            steps{
                script{
                    echo "deploying the application"
                   script{
                        sh 'docker login -u haifa123456 -p haifabrineg'
                        sh 'docker build -t haifa123456/angular-app:1.0 .'
                        sh 'docker push haifa123456/angular-app:1.0'

                }
            }
        }
    }
}
}
