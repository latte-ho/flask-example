node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("latte-ho/flask-example")
         
     }
     stage('Push image') {
         docker.withRegistry('http://ec2-13-125-243-107.ap-northeast-2.compute.amazonaws.com', 'harbor-reg') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}
