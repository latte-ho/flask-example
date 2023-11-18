node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("latte-ho/flask-example")
         
     }
     stage('Push image') {
         docker.withRegistry('https://git-codecommit.ap-northeast-2.amazonaws.com/v1/repos/product-app', 'harbor-reg') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}
