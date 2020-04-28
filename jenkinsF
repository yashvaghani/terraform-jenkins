node {
   stage('Checkout') {
       echo 'Hello from Stage 1'
       cleanWs()
      checkout scm
   }
   stage('Set Terraform path') {
      script {
         def tfHome = tool name: 'Terraform'
         env.PATH = "${tfHome}:${env.PATH}"
    }
 }
    stage('init') {
        // echo env.AWS_ACCESS_KEY_ID
        // echo env.AWS_SECRET_ACCESS_KEY
        sh 'terraform init'
    }
    stage('plan') {
        sh 'terraform plan'
    }
     stage('plan') {
        sh 'terraform apply -auto-approve'
    }
}
