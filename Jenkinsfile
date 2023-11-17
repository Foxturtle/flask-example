node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("admin/flask-example")
         
     }
     stage('Push image') {
         docker.withRegistry('https://54.180.139.225/', 'harbor_cred') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}

stage('Build image') {
    app = docker.build("admin/flask-example")

}
stage('Push image') {
    docker.withRegistry('https://54.180.139.225/', 'harbor_cred') {
        app.push("${env.BUILD_NUMBER}")
        app.push("latest")
    }
}
