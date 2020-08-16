pipeline{
    agent any
    environment{
       PATH = "/usr/share/maven/bin:$PATH"
    }
    stages{
       stage("Git Checkout"){
          steps{
           git credentialsId: '5a45ed6e-ad7f-44cc-b75a-e0c9515199a3', url: 'https://github.com/aifemunshi/awscicdproject.git'
          }
       }
      stage("Maven Build"){
         steps{
            sh "mvn clean install"
         }  
      }
      stage("Jar Run"){
         steps{
           sh "cd /var/lib/jenkins/workspace/PathologyBackendProject/target/"
           sh "sudo nohup java -jar aws-elastic-beanstalk-example-2-0.0.1-SNAPSHOT.jar"
         }
      }
    }
}
